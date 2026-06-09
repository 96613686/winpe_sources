# CSsdpSearchSocketManager::GetReadableSocketCount(void)

- ea: `0x180007b50`
- end: `0x180007ce5`
- name: `?GetReadableSocketCount@CSsdpSearchSocketManager@@QEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(CSsdpSearchSocketManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800070d0`

## callees

- `0x180007b50`
- `0x18000e3bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c4b`
- `WS2_32!__imp_select` at `0x180007c39`
- `WS2_32!__imp_select` at `0x180007c39`

## pseudocode

```c
__int64 __fastcall CSsdpSearchSocketManager::GetReadableSocketCount(CSsdpSearchSocketManager *this)
{
  int v2; // r10d
  int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r9
  int i; // r8d
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // edx
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int v14; // edx
  unsigned int v15; // r11d
  timeval timeout; // [rsp+50h] [rbp+8h] BYREF

  timeout = (timeval)60LL;
  if ( *((_DWORD *)this + 18) )
    CSsdpSearchSocketManager::ClearOld(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = *((_DWORD *)this + 14);
  v3 = 0;
  *((_DWORD *)this + 20) = 1;
  *((_DWORD *)this + 21) = 0;
  *((_DWORD *)this + 22) = 0;
  if ( v2 > 0 )
  {
    v4 = 0;
    do
    {
      v5 = *((_QWORD *)this + 6) + 32 * v4;
      if ( *(_WORD *)(v5 + 24) == 2 )
      {
        v14 = *((_DWORD *)this + 22);
        v15 = 0;
        if ( v14 )
        {
          while ( *((_QWORD *)this + v15 + 12) != *(_QWORD *)v5 )
          {
            if ( ++v15 >= v14 )
              goto LABEL_18;
          }
        }
        else
        {
LABEL_18:
          if ( v15 == v14 && v14 < 0x40 )
          {
            *((_QWORD *)this + v15 + 12) = *(_QWORD *)v5;
            ++*((_DWORD *)this + 22);
          }
        }
      }
      ++v3;
      ++v4;
    }
    while ( v3 < v2 );
    v6 = 0;
    for ( i = 0; i < v2; ++i )
    {
      v8 = *((_QWORD *)this + 6);
      v9 = 32 * v6;
      if ( *(_WORD *)(32 * v6 + v8 + 24) != 2 )
      {
        v10 = *((_DWORD *)this + 22);
        v11 = 0;
        if ( v10 )
        {
          while ( *((_QWORD *)this + v11 + 12) != *(_QWORD *)(v9 + v8) )
          {
            v11 = (unsigned int)(v11 + 1);
            if ( (unsigned int)v11 >= v10 )
              goto LABEL_12;
          }
        }
        else
        {
LABEL_12:
          if ( (_DWORD)v11 == v10 && v10 < 0x40 )
          {
            *((_QWORD *)this + v11 + 12) = *(_QWORD *)(v9 + v8);
            ++*((_DWORD *)this + 22);
          }
        }
      }
      ++v6;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v12 = select(-1, (fd_set *)((char *)this + 88), 0, 0, &timeout);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_DWORD *)this + 20) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v12;
}

```

## disassembly

```asm
0x180007b50  mov     [rsp+arg_8], rbx
0x180007b55  mov     [rsp+arg_10], rbp
0x180007b5a  push    rsi
0x180007b5b  push    rdi
0x180007b5c  push    r14
0x180007b5e  sub     rsp, 30h
0x180007b62  xor     ebp, ebp
0x180007b64  mov     qword ptr [rsp+48h+arg_0.tv_sec], 3Ch ; '<'
0x180007b6d  mov     rsi, rcx
0x180007b70  cmp     [rcx+48h], ebp
0x180007b73  jnz     loc_180007CDB
0x180007b79  lea     rcx, [rsi+8]; lpCriticalSection
0x180007b7d  call    cs:__imp_EnterCriticalSection
0x180007b84  nop     dword ptr [rax+rax+00h]
0x180007b89  mov     r10d, [rsi+38h]
0x180007b8d  mov     eax, ebp
0x180007b8f  mov     dword ptr [rsi+50h], 1
0x180007b96  mov     [rsi+54h], ebp
0x180007b99  mov     [rsi+58h], ebp
0x180007b9c  test    r10d, r10d
0x180007b9f  jle     short loc_180007C10
0x180007ba1  mov     r8, rbp
0x180007ba4  mov     r9, r8
0x180007ba7  shl     r9, 5
0x180007bab  add     r9, [rsi+30h]
0x180007baf  cmp     word ptr [r9+18h], 2
0x180007bb5  jz      loc_180007C80
0x180007bbb  inc     eax
0x180007bbd  inc     r8
0x180007bc0  cmp     eax, r10d
0x180007bc3  jl      short loc_180007BA4
0x180007bc5  mov     r9, rbp
0x180007bc8  mov     r8d, ebp
0x180007bcb  mov     rax, [rsi+30h]
0x180007bcf  mov     rdi, r9
0x180007bd2  shl     rdi, 5
0x180007bd6  cmp     word ptr [rdi+rax+18h], 2
0x180007bdc  jz      short loc_180007C05
0x180007bde  mov     edx, [rsi+58h]
0x180007be1  mov     ecx, ebp
0x180007be3  test    edx, edx
0x180007be5  jz      short loc_180007BF8
0x180007be7  mov     r11, [rdi+rax]
0x180007beb  cmp     [rsi+rcx*8+60h], r11
0x180007bf0  jz      short loc_180007C05
0x180007bf2  inc     ecx
0x180007bf4  cmp     ecx, edx
0x180007bf6  jb      short loc_180007BEB
0x180007bf8  cmp     ecx, edx
0x180007bfa  jnz     short loc_180007C05
0x180007bfc  cmp     edx, 40h ; '@'
0x180007bff  jb      loc_180007CCA
0x180007c05  inc     r8d
0x180007c08  inc     r9
0x180007c0b  cmp     r8d, r10d
0x180007c0e  jl      short loc_180007BCB
0x180007c10  lea     rcx, [rsi+8]; lpCriticalSection
0x180007c14  call    cs:__imp_LeaveCriticalSection
0x180007c1b  nop     dword ptr [rax+rax+00h]
0x180007c20  lea     rax, [rsp+48h+arg_0]
0x180007c25  xor     r9d, r9d; exceptfds
0x180007c28  xor     r8d, r8d; writefds
0x180007c2b  mov     [rsp+48h+timeout], rax; timeout
0x180007c30  lea     rdx, [rsi+58h]; readfds
0x180007c34  mov     ecx, 0FFFFFFFFh; nfds
0x180007c39  call    cs:__imp_select
0x180007c40  nop     dword ptr [rax+rax+00h]
0x180007c45  lea     rcx, [rsi+8]; lpCriticalSection
0x180007c49  mov     edi, eax
0x180007c4b  call    cs:__imp_EnterCriticalSection
0x180007c52  nop     dword ptr [rax+rax+00h]
0x180007c57  lea     rcx, [rsi+8]; lpCriticalSection
0x180007c5b  mov     [rsi+50h], ebp
0x180007c5e  call    cs:__imp_LeaveCriticalSection
0x180007c65  nop     dword ptr [rax+rax+00h]
0x180007c6a  mov     rbx, [rsp+48h+arg_8]
0x180007c6f  mov     eax, edi
0x180007c71  mov     rbp, [rsp+48h+arg_10]
0x180007c76  add     rsp, 30h
0x180007c7a  pop     r14
0x180007c7c  pop     rdi
0x180007c7d  pop     rsi
0x180007c7e  retn
0x180007c80  mov     edx, [rsi+58h]
0x180007c83  mov     r11d, ebp
0x180007c86  test    edx, edx
0x180007c88  jnz     short loc_180007CAF
0x180007c8a  cmp     r11d, edx
0x180007c8d  jnz     loc_180007BBB
0x180007c93  cmp     edx, 40h ; '@'
0x180007c96  jnb     loc_180007BBB
0x180007c9c  mov     rcx, [r9]
0x180007c9f  mov     edx, r11d
0x180007ca2  mov     [rsi+rdx*8+60h], rcx
0x180007ca7  inc     dword ptr [rsi+58h]
0x180007caa  jmp     loc_180007BBB
0x180007caf  mov     rdi, [r9]
0x180007cb2  mov     ecx, r11d; this
0x180007cb5  cmp     [rsi+rcx*8+60h], rdi
0x180007cba  jz      loc_180007BBB
0x180007cc0  inc     r11d
0x180007cc3  cmp     r11d, edx
0x180007cc6  jb      short loc_180007CB2
0x180007cc8  jmp     short loc_180007C8A
0x180007cca  mov     rax, [rdi+rax]
0x180007cce  mov     [rsi+rcx*8+60h], rax
0x180007cd3  inc     dword ptr [rsi+58h]
0x180007cd6  jmp     loc_180007C05
0x180007cdb  call    ?ClearOld@CSsdpSearchSocketManager@@AEAAXXZ; CSsdpSearchSocketManager::ClearOld(void)
0x180007ce0  jmp     loc_180007B79
```
