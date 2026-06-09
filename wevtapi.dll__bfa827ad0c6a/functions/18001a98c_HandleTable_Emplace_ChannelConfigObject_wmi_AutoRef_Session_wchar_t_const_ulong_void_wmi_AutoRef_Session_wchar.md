# HandleTable::Emplace<ChannelConfigObject,wmi::AutoRef<Session> &,wchar_t const * &,ulong &>(void * &,wmi::AutoRef<Session> &,wchar_t const * &,ulong &)

- ea: `0x18001a98c`
- end: `0x18001ab11`
- name: `??$Emplace@VChannelConfigObject@@AEAV?$AutoRef@VSession@@@wmi@@AEAPEB_WAEAK@HandleTable@@QEAAPEAVChannelConfigObject@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@AEAPEB_WAEAK@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001a750`

## callees

- `0x180007180`
- `0x18000c55c`
- `0x18001a98c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a9be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a9be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aaf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aaf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ChannelConfigObject *__fastcall HandleTable::Emplace<ChannelConfigObject,wmi::AutoRef<Session> &,wchar_t const * &,unsigned long &>(
        __int64 a1,
        unsigned __int64 *a2,
        struct Session **a3,
        const wchar_t **a4,
        int *a5)
{
  int i; // edi
  __int64 v9; // rsi
  int v10; // ebx
  _DWORD *v11; // rdx
  int j; // ecx
  __int64 v13; // rax
  __int64 v14; // rax
  ChannelConfigObject *v15; // rax
  ChannelConfigObject *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx

  AcquireSRWLockExclusive(&g_objectTable);
  for ( i = 0; i < 24; ++i )
  {
    v9 = 24LL * i;
    if ( !*(_QWORD *)((char *)&g_objectTable + v9 + 16) )
    {
      v10 = 64 << i;
      v11 = MIDL_user_allocate(saturated_mul(64 << i, 0x10u));
      if ( !v11 )
        break;
      for ( j = 0; j < v10 - 1; v11[2 * v13 + 2] = j )
      {
        v13 = 2LL * (unsigned int)j;
        LOBYTE(v11[2 * v13]) = 0;
        ++j;
      }
      v14 = 2LL * j;
      LOBYTE(v11[2 * v14]) = 0;
      v11[2 * v14 + 2] = -1;
      *(_DWORD *)((char *)&g_objectTable + v9 + 28) = 0;
      *(_DWORD *)((char *)&g_objectTable + v9 + 8) = v10;
      *(RTL_SRWLOCK *)((char *)&g_objectTable + v9 + 16) = (RTL_SRWLOCK)v11;
    }
    if ( dword_18004B3AC[6 * i] != -1 )
    {
      v15 = (ChannelConfigObject *)MIDL_user_allocate(0x78u);
      if ( v15 )
        v16 = ChannelConfigObject::ChannelConfigObject(v15, *a3, *a4, *a5);
      else
        v16 = 0;
      if ( v16 )
      {
        v17 = *(int *)((char *)&g_objectTable + v9 + 28);
        *a2 = (unsigned int)(i << 24) | (unsigned __int64)(((_DWORD)v17 + 1) & 0xFFFFFF);
        v18 = 2 * v17;
        v19 = *(__int64 *)((char *)&g_objectTable + v9 + 16);
        *(_DWORD *)((char *)&g_objectTable + v9 + 28) = *(_DWORD *)(v19 + 16 * v17 + 8);
        *(_BYTE *)(v19 + 8 * v18) = 1;
        *(_QWORD *)(v19 + 8 * v18 + 8) = v16;
        ++*(_DWORD *)((char *)&g_objectTable + v9 + 24);
        goto LABEL_16;
      }
      break;
    }
  }
  v16 = 0;
LABEL_16:
  ReleaseSRWLockExclusive(&g_objectTable);
  return v16;
}

```

## disassembly

```asm
0x18001a98c  mov     rax, rsp
0x18001a98f  mov     [rax+10h], rbx
0x18001a993  mov     [rax+18h], rbp
0x18001a997  mov     [rax+8], rcx
0x18001a99b  push    rsi
0x18001a99c  push    rdi
0x18001a99d  push    r13
0x18001a99f  push    r14
0x18001a9a1  push    r15
0x18001a9a3  sub     rsp, 30h
0x18001a9a7  mov     r14, r9
0x18001a9aa  mov     r15, r8
0x18001a9ad  mov     rbp, rdx
0x18001a9b0  lea     r13, ?g_objectTable@@3VObjectTable@@A; ObjectTable g_objectTable
0x18001a9b7  mov     [rax+8], r13
0x18001a9bb  mov     rcx, r13; SRWLock
0x18001a9be  call    cs:__imp_AcquireSRWLockExclusive
0x18001a9c4  nop
0x18001a9c5  xor     edi, edi
0x18001a9c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a9cb  cmp     edi, 18h
0x18001a9ce  jge     loc_18001AAEC
0x18001a9d4  movsxd  rax, edi
0x18001a9d7  lea     rcx, [rax+rax*2]
0x18001a9db  lea     rsi, ds:0[rcx*8]
0x18001a9e3  cmp     qword ptr [rsi+r13+10h], 0
0x18001a9e9  jnz     short loc_18001AA5C
0x18001a9eb  mov     ecx, edi
0x18001a9ed  mov     ebx, 40h ; '@'
0x18001a9f2  shl     ebx, cl
0x18001a9f4  movsxd  rcx, ebx
0x18001a9f7  mov     eax, 10h
0x18001a9fc  mul     rcx
0x18001a9ff  cmovb   rax, r8
0x18001aa03  mov     rcx, rax; size
0x18001aa06  call    MIDL_user_allocate
0x18001aa0b  mov     rdx, rax
0x18001aa0e  test    rax, rax
0x18001aa11  jz      loc_18001AAEC
0x18001aa17  xor     ecx, ecx
0x18001aa19  lea     r8d, [rbx-1]
0x18001aa1d  test    r8d, r8d
0x18001aa20  jle     short loc_18001AA36
0x18001aa22  mov     eax, ecx
0x18001aa24  add     rax, rax
0x18001aa27  mov     byte ptr [rdx+rax*8], 0
0x18001aa2b  inc     ecx
0x18001aa2d  mov     [rdx+rax*8+8], ecx
0x18001aa31  cmp     ecx, r8d
0x18001aa34  jl      short loc_18001AA22
0x18001aa36  movsxd  rax, ecx
0x18001aa39  add     rax, rax
0x18001aa3c  mov     byte ptr [rdx+rax*8], 0
0x18001aa40  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001aa44  mov     [rdx+rax*8+8], r8d
0x18001aa49  mov     dword ptr [rsi+r13+1Ch], 0
0x18001aa52  mov     [rsi+r13+8], ebx
0x18001aa57  mov     [rsi+r13+10h], rdx
0x18001aa5c  lea     rcx, dword_18004B3AC
0x18001aa63  mov     rax, rsi
0x18001aa66  cmp     dword ptr [rcx+rax], 0FFFFFFFFh
0x18001aa6a  jnz     short loc_18001AA73
0x18001aa6c  inc     edi
0x18001aa6e  jmp     loc_18001A9CB
0x18001aa73  mov     ecx, 78h ; 'x'; size
0x18001aa78  call    MIDL_user_allocate
0x18001aa7d  mov     [rsp+58h+var_38], rax
0x18001aa82  test    rax, rax
0x18001aa85  jz      short loc_18001AAA5
0x18001aa87  mov     r9, [rsp+58h+arg_20]
0x18001aa8f  mov     r9d, [r9]; unsigned int
0x18001aa92  mov     r8, [r14]; wchar_t *
0x18001aa95  mov     rdx, [r15]; struct Session *
0x18001aa98  mov     rcx, rax; this
0x18001aa9b  call    ??0ChannelConfigObject@@QEAA@PEAVSession@@PEB_WK@Z; ChannelConfigObject::ChannelConfigObject(Session *,wchar_t const *,ulong)
0x18001aaa0  mov     rbx, rax
0x18001aaa3  jmp     short loc_18001AAA7
0x18001aaa5  xor     ebx, ebx
0x18001aaa7  test    rbx, rbx
0x18001aaaa  jz      short loc_18001AAEC
0x18001aaac  movsxd  rdx, dword ptr [rsi+r13+1Ch]
0x18001aab1  lea     ecx, [rdx+1]
0x18001aab4  and     ecx, 0FFFFFFh
0x18001aaba  shl     edi, 18h
0x18001aabd  mov     eax, edi
0x18001aabf  or      rcx, rax
0x18001aac2  mov     [rbp+0], rcx
0x18001aac6  mov     r8, rdx
0x18001aac9  add     r8, r8
0x18001aacc  mov     rcx, [rsi+r13+10h]
0x18001aad1  mov     eax, [rcx+r8*8+8]
0x18001aad6  mov     [rsi+r13+1Ch], eax
0x18001aadb  mov     byte ptr [rcx+r8*8], 1
0x18001aae0  mov     [rcx+r8*8+8], rbx
0x18001aae5  inc     dword ptr [rsi+r13+18h]
0x18001aaea  jmp     short loc_18001AAEE
0x18001aaec  xor     ebx, ebx
0x18001aaee  mov     rcx, r13; SRWLock
0x18001aaf1  call    cs:__imp_ReleaseSRWLockExclusive
0x18001aaf7  mov     rax, rbx
0x18001aafa  mov     rbx, [rsp+58h+arg_8]
0x18001aaff  mov     rbp, [rsp+58h+arg_10]
0x18001ab04  add     rsp, 30h
0x18001ab08  pop     r15
0x18001ab0a  pop     r14
0x18001ab0c  pop     r13
0x18001ab0e  pop     rdi
0x18001ab0f  pop     rsi
0x18001ab10  retn
```
