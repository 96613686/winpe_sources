# RtmCleanupInstances

- ea: `0x180007c50`
- end: `0x180007e3e`
- name: `RtmCleanupInstances`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007840`

## callees

- `0x180007c50`
- `0x18000995c`
- `0x180009adc`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007c77`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007dad`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007c77`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007dad`
- `ntdll!RtlReleaseResource` at `0x180007ce6`
- `ntdll!RtlReleaseResource` at `0x180007e27`
- `ntdll!RtlReleaseResource` at `0x180007ce6`
- `ntdll!RtlReleaseResource` at `0x180007e27`
- `KERNEL32!DeleteTimerQueueEx` at `0x180007cfc`
- `KERNEL32!DeleteTimerQueueEx` at `0x180007d1d`
- `KERNEL32!DeleteTimerQueueEx` at `0x180007cfc`
- `KERNEL32!DeleteTimerQueueEx` at `0x180007d1d`

## pseudocode

```c
void RtmCleanupInstances()
{
  int v0; // eax
  int v1; // ecx
  unsigned int v2; // ebp
  __int64 *v3; // rdi
  __int64 **v4; // r14
  volatile signed __int32 *v5; // r15
  volatile signed __int32 *v6; // rbx
  void *v7; // rcx
  void *v8; // rcx
  int v9; // eax
  int v10; // edi
  unsigned int v11; // r12d
  volatile signed __int32 *v12; // rsi
  volatile signed __int32 *v13; // r13
  char *v14; // rcx
  _QWORD *v15; // rsi
  char *v16; // rcx
  __int64 *v17; // rsi
  __int64 *v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+80h] [rbp+8h]
  int v20; // [rsp+88h] [rbp+10h]
  int v21; // [rsp+90h] [rbp+18h]
  int v22; // [rsp+98h] [rbp+20h]

  if ( HIDWORD(qword_18002BD00) )
  {
    RtlAcquireResourceExclusive(&Resource, 1u);
    v20 = HIDWORD(qword_18002BD00);
    v0 = 0;
    v1 = HIDWORD(qword_18002BD00);
    v2 = 0;
    v21 = 0;
    v19 = 0;
    do
    {
      v3 = &qword_18002BD08[2 * v2];
      v18 = v3;
      v4 = (__int64 **)*v3;
      if ( (__int64 *)*v3 != v3 )
      {
        do
        {
          v5 = (volatile signed __int32 *)v4[3];
          if ( v5 == (volatile signed __int32 *)(v4 + 3) )
          {
            v17 = *v4;
          }
          else
          {
            do
            {
              v6 = v5 - 6;
              _InterlockedIncrement(v5 - 6);
              RtlReleaseResource(&Resource);
              v7 = (void *)*((_QWORD *)v5 + 88);
              if ( v7 )
              {
                DeleteTimerQueueEx(v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
                *((_QWORD *)v6 + 91) = 0;
              }
              v8 = (void *)*((_QWORD *)v6 + 92);
              if ( v8 )
              {
                DeleteTimerQueueEx(v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
                *((_QWORD *)v6 + 92) = 0;
              }
              v9 = *((_DWORD *)v6 + 82);
              v10 = 0;
              v11 = 0;
              v22 = v9;
              do
              {
                v12 = &v6[4 * v11 + 84];
                v13 = *(volatile signed __int32 **)v12;
                if ( *(volatile signed __int32 **)v12 != v12 )
                {
                  do
                  {
                    v14 = (char *)(v13 - 6);
                    v13 = *(volatile signed __int32 **)v13;
                    *(_DWORD *)v14 = 0;
                    DestroyEntity(v14);
                    ++v10;
                  }
                  while ( v13 != v12 );
                  v9 = v22;
                }
                if ( v10 == v9 )
                  break;
                ++v11;
              }
              while ( v11 < 0x10 );
              v15 = v6 + 148;
              while ( (_QWORD *)*v15 != v15 )
              {
                v16 = (char *)(*v15 - 24LL);
                *(_DWORD *)v16 = 0;
                DestroyEntity(v16);
              }
              RtlAcquireResourceExclusive(&Resource, 1u);
              v5 = *(volatile signed __int32 **)v5;
              v17 = *v4;
              if ( _InterlockedExchangeAdd(v6, 0xFFFFFFFF) == 1 )
                DestroyAddressFamily((char *)v6);
            }
            while ( v5 != (volatile signed __int32 *)(v4 + 3) );
            v3 = v18;
            v0 = v19;
          }
          ++v0;
          v4 = (__int64 **)v17;
          v19 = v0;
        }
        while ( v17 != v3 );
        v2 = v21;
        v1 = v20;
      }
      if ( v0 == v1 )
        break;
      v21 = ++v2;
    }
    while ( !v2 );
    RtlReleaseResource(&Resource);
  }
}

```

## disassembly

```asm
0x180007c50  push    rbx
0x180007c52  push    rbp
0x180007c53  push    rsi
0x180007c54  push    rdi
0x180007c55  push    r12
0x180007c57  push    r13
0x180007c59  push    r14
0x180007c5b  push    r15
0x180007c5d  sub     rsp, 38h
0x180007c61  cmp     dword ptr cs:qword_18002BD00+4, 0
0x180007c68  jz      loc_180007E2D
0x180007c6e  mov     dl, 1; Wait
0x180007c70  lea     rcx, Resource; Resource
0x180007c77  call    cs:__imp_RtlAcquireResourceExclusive
0x180007c7d  mov     eax, dword ptr cs:qword_18002BD00+4
0x180007c83  mov     [rsp+78h+arg_8], eax
0x180007c8a  xor     eax, eax
0x180007c8c  mov     ecx, [rsp+78h+arg_8]
0x180007c93  xor     ebp, ebp
0x180007c95  mov     [rsp+78h+arg_10], ebp
0x180007c9c  mov     [rsp+78h+arg_0], eax
0x180007ca3  mov     edi, ebp
0x180007ca5  lea     rdx, qword_18002BD08
0x180007cac  shl     rdi, 4
0x180007cb0  add     rdi, rdx
0x180007cb3  mov     [rsp+78h+var_58], rdi
0x180007cb8  mov     r14, [rdi]
0x180007cbb  cmp     r14, rdi
0x180007cbe  jz      loc_180007E0A
0x180007cc4  lea     rcx, [r14+18h]
0x180007cc8  mov     r15, [rcx]
0x180007ccb  cmp     r15, rcx
0x180007cce  jz      loc_180007DE4
0x180007cd4  lea     rbp, [r14+18h]
0x180007cd8  lea     rbx, [r15-18h]
0x180007cdc  lock inc dword ptr [rbx]
0x180007cdf  lea     rcx, Resource; Resource
0x180007ce6  call    cs:__imp_RtlReleaseResource
0x180007cec  mov     rcx, [rbx+2D8h]; TimerQueue
0x180007cf3  test    rcx, rcx
0x180007cf6  jz      short loc_180007D0D
0x180007cf8  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180007cfc  call    cs:__imp_DeleteTimerQueueEx
0x180007d02  mov     qword ptr [rbx+2D8h], 0
0x180007d0d  mov     rcx, [rbx+2E0h]; TimerQueue
0x180007d14  test    rcx, rcx
0x180007d17  jz      short loc_180007D2E
0x180007d19  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180007d1d  call    cs:__imp_DeleteTimerQueueEx
0x180007d23  mov     qword ptr [rbx+2E0h], 0
0x180007d2e  mov     eax, [rbx+148h]
0x180007d34  xor     edi, edi
0x180007d36  xor     r12d, r12d
0x180007d39  mov     [rsp+78h+arg_18], eax
0x180007d40  mov     esi, r12d
0x180007d43  add     rsi, 15h
0x180007d47  shl     rsi, 4
0x180007d4b  add     rsi, rbx
0x180007d4e  mov     r13, [rsi]
0x180007d51  cmp     r13, rsi
0x180007d54  jz      short loc_180007D77
0x180007d56  lea     rcx, [r13-18h]; lpMem
0x180007d5a  mov     r13, [r13+0]
0x180007d5e  mov     dword ptr [rcx], 0
0x180007d64  call    DestroyEntity
0x180007d69  inc     edi
0x180007d6b  cmp     r13, rsi
0x180007d6e  jnz     short loc_180007D56
0x180007d70  mov     eax, [rsp+78h+arg_18]
0x180007d77  cmp     edi, eax
0x180007d79  jz      short loc_180007D84
0x180007d7b  inc     r12d
0x180007d7e  cmp     r12d, 10h
0x180007d82  jb      short loc_180007D40
0x180007d84  lea     rsi, [rbx+250h]
0x180007d8b  mov     rcx, [rsi]
0x180007d8e  cmp     rcx, rsi
0x180007d91  jz      short loc_180007DA4
0x180007d93  add     rcx, 0FFFFFFFFFFFFFFE8h; lpMem
0x180007d97  mov     dword ptr [rcx], 0
0x180007d9d  call    DestroyEntity
0x180007da2  jmp     short loc_180007D8B
0x180007da4  mov     dl, 1; Wait
0x180007da6  lea     rcx, Resource; Resource
0x180007dad  call    cs:__imp_RtlAcquireResourceExclusive
0x180007db3  mov     r15, [r15]
0x180007db6  or      eax, 0FFFFFFFFh
0x180007db9  mov     rsi, [r14]
0x180007dbc  lock xadd [rbx], eax
0x180007dc0  cmp     eax, 1
0x180007dc3  jnz     short loc_180007DCD
0x180007dc5  mov     rcx, rbx; lpMem
0x180007dc8  call    DestroyAddressFamily
0x180007dcd  cmp     r15, rbp
0x180007dd0  jnz     loc_180007CD8
0x180007dd6  mov     rdi, [rsp+78h+var_58]
0x180007ddb  mov     eax, [rsp+78h+arg_0]
0x180007de2  jmp     short loc_180007DE7
0x180007de4  mov     rsi, [r14]
0x180007de7  inc     eax
0x180007de9  mov     r14, rsi
0x180007dec  mov     [rsp+78h+arg_0], eax
0x180007df3  cmp     rsi, rdi
0x180007df6  jnz     loc_180007CC4
0x180007dfc  mov     ebp, [rsp+78h+arg_10]
0x180007e03  mov     ecx, [rsp+78h+arg_8]
0x180007e0a  cmp     eax, ecx
0x180007e0c  jz      short loc_180007E20
0x180007e0e  inc     ebp
0x180007e10  mov     [rsp+78h+arg_10], ebp
0x180007e17  cmp     ebp, 1
0x180007e1a  jb      loc_180007CA3
0x180007e20  lea     rcx, Resource; Resource
0x180007e27  call    cs:__imp_RtlReleaseResource
0x180007e2d  add     rsp, 38h
0x180007e31  pop     r15
0x180007e33  pop     r14
0x180007e35  pop     r13
0x180007e37  pop     r12
0x180007e39  pop     rdi
0x180007e3a  pop     rsi
0x180007e3b  pop     rbp
0x180007e3c  pop     rbx
0x180007e3d  retn
```
