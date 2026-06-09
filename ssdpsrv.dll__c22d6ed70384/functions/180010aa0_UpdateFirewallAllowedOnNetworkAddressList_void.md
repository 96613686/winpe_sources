# UpdateFirewallAllowedOnNetworkAddressList(void)

- ea: `0x180010aa0`
- end: `0x180010cd7`
- name: `?UpdateFirewallAllowedOnNetworkAddressList@@YAXXZ`
- size: `567`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000eec0`
- `0x180010890`

## callees

- `0x180010a30`
- `0x180010aa0`
- `0x180010ce0`
- `0x18002c90c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010b62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010b62`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010af0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010af0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010bfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010bfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010abb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010abb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010b40`

## pseudocode

```c
void UpdateFirewallAllowedOnNetworkAddressList(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // ebp
  struct _SSDPNetwork *v2; // rdi
  int v3; // esi
  struct _SSDPNetwork *i; // rax
  struct AllowedInterface *v5; // rbx
  int v6; // edx
  unsigned int v7; // r8d
  struct _SSDPNetwork *v8; // r10
  struct _SSDPNetwork *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int j; // r14d
  struct _SSDPNetwork *v15; // rdi
  char *v16; // rsi
  struct _SSDPNetwork *v17; // r9
  __int64 v18; // rax
  BOOL v19; // ecx

  v0 = 0;
  v1 = 0;
  EnterCriticalSection(&stru_180042240);
  v2 = qword_180042230;
  v3 = dword_180042628;
  for ( i = qword_180042230; i != (struct _SSDPNetwork *)&qword_180042230; ++v0 )
    i = *(struct _SSDPNetwork **)i;
  v5 = (struct AllowedInterface *)malloc(28LL * v0);
  if ( !v5 || v2 == (struct _SSDPNetwork *)&qword_180042230 )
  {
    LeaveCriticalSection(&stru_180042240);
    if ( !v5 )
      return;
  }
  else
  {
    do
    {
      v6 = 0;
      v7 = 0;
      v8 = v2;
      v9 = v2;
      v2 = *(struct _SSDPNetwork **)v2;
      if ( v1 )
      {
        do
        {
          v10 = 28LL * v7;
          v11 = *(_QWORD *)((char *)v9 + 244) - *(_QWORD *)((char *)v5 + v10);
          if ( !v11 )
            v11 = *(_QWORD *)((char *)v9 + 252) - *(_QWORD *)((char *)v5 + v10 + 8);
          if ( !v11 )
            v6 = 1;
          ++v7;
        }
        while ( v7 < v1 );
        if ( v6 )
          continue;
      }
      if ( !(unsigned int)AddressIsLoopback((const struct sockaddr *)((char *)v8 + 24)) )
      {
        v13 = 28LL * v1++;
        *(_OWORD *)((char *)v5 + v13) = *(_OWORD *)(v12 + 244);
        *(_QWORD *)((char *)v5 + v13 + 20) = 0;
      }
    }
    while ( v2 != (struct _SSDPNetwork *)&qword_180042230 );
    LeaveCriticalSection(&stru_180042240);
  }
  if ( !(unsigned int)CFirewallManager::CheckAllowedInterfaces(
                        (CFirewallManager *)&CFirewallManager::s_instance,
                        1900,
                        17,
                        v1,
                        v5) )
  {
    EnterCriticalSection(&stru_180042240);
    if ( v3 == dword_180042628 )
    {
      for ( j = 0; j < v1; ++j )
      {
        v15 = qword_180042230;
        if ( qword_180042230 != (struct _SSDPNetwork *)&qword_180042230 )
        {
          v16 = (char *)v5 + 28 * j;
          do
          {
            v17 = v15;
            v15 = *(struct _SSDPNetwork **)v15;
            v18 = *(_QWORD *)((char *)v17 + 244) - *(_QWORD *)v16;
            if ( !v18 )
              v18 = *(_QWORD *)((char *)v17 + 252) - *((_QWORD *)v16 + 1);
            if ( !v18 )
            {
              v19 = *((_DWORD *)v16 + 5) && !*((_DWORD *)v16 + 6);
              *((_DWORD *)v17 + 65) = v19;
              *((_DWORD *)v17 + 66) = *((_DWORD *)v16 + 4);
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  (unsigned int)WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids,
                  *((_QWORD *)v17 + 28),
                  v19);
              }
            }
          }
          while ( v15 != (struct _SSDPNetwork *)&qword_180042230 );
        }
      }
    }
    LeaveCriticalSection(&stru_180042240);
  }
  free(v5);
}

```

## disassembly

```asm
0x180010aa0  mov     [rsp+arg_10], rbx
0x180010aa5  push    rbp
0x180010aa6  push    rsi
0x180010aa7  push    rdi
0x180010aa8  push    r12
0x180010aaa  push    r15
0x180010aac  sub     rsp, 30h
0x180010ab0  lea     rcx, stru_180042240; lpCriticalSection
0x180010ab7  xor     ebx, ebx
0x180010ab9  xor     ebp, ebp
0x180010abb  call    cs:__imp_EnterCriticalSection
0x180010ac1  mov     rdi, cs:qword_180042230
0x180010ac8  lea     r15, qword_180042230
0x180010acf  mov     esi, cs:dword_180042628
0x180010ad5  mov     rax, rdi
0x180010ad8  cmp     rdi, r15
0x180010adb  jz      short loc_180010AEA
0x180010add  nop     dword ptr [rax]
0x180010ae0  mov     rax, [rax]
0x180010ae3  inc     ebx
0x180010ae5  cmp     rax, r15
0x180010ae8  jnz     short loc_180010AE0
0x180010aea  mov     eax, ebx
0x180010aec  imul    rcx, rax, 1Ch; Size
0x180010af0  call    cs:__imp_malloc
0x180010af6  mov     rbx, rax
0x180010af9  mov     r12d, 1
0x180010aff  test    rax, rax
0x180010b02  jnz     short loc_180010B79
0x180010b04  lea     rcx, stru_180042240; lpCriticalSection
0x180010b0b  call    cs:__imp_LeaveCriticalSection
0x180010b11  test    rbx, rbx
0x180010b14  jz      short loc_180010B68
0x180010b16  mov     edx, 76Ch; unsigned __int16
0x180010b1b  mov     [rsp+58h+var_38], rbx; struct AllowedInterface *
0x180010b20  mov     r8d, 11h; unsigned __int16
0x180010b26  lea     rcx, ?s_instance@CFirewallManager@@0V1@A; this
0x180010b2d  mov     r9d, ebp; unsigned int
0x180010b30  call    ?CheckAllowedInterfaces@CFirewallManager@@AEAAKGGKPEAUAllowedInterface@@@Z; CFirewallManager::CheckAllowedInterfaces(ushort,ushort,ulong,AllowedInterface *)
0x180010b35  test    eax, eax
0x180010b37  jnz     short loc_180010B5F
0x180010b39  lea     rcx, stru_180042240; lpCriticalSection
0x180010b40  call    cs:__imp_EnterCriticalSection
0x180010b46  cmp     esi, cs:dword_180042628
0x180010b4c  jz      loc_180010C06
0x180010b52  lea     rcx, stru_180042240; lpCriticalSection
0x180010b59  call    cs:__imp_LeaveCriticalSection
0x180010b5f  mov     rcx, rbx; Block
0x180010b62  call    cs:__imp_free
0x180010b68  mov     rbx, [rsp+58h+arg_10]
0x180010b6d  add     rsp, 30h
0x180010b71  pop     r15
0x180010b73  pop     r12
0x180010b75  pop     rdi
0x180010b76  pop     rsi
0x180010b77  pop     rbp
0x180010b78  retn
0x180010b79  cmp     rdi, r15
0x180010b7c  jz      short loc_180010B04
0x180010b7e  xchg    ax, ax
0x180010b80  xor     edx, edx
0x180010b82  xor     r8d, r8d
0x180010b85  mov     r10, rdi
0x180010b88  mov     r9, rdi
0x180010b8b  mov     rdi, [rdi]
0x180010b8e  test    ebp, ebp
0x180010b90  jz      short loc_180010BC5
0x180010b92  mov     eax, r8d
0x180010b95  imul    rcx, rax, 1Ch
0x180010b99  mov     rax, [r9+0F4h]
0x180010ba0  sub     rax, [rcx+rbx]
0x180010ba4  jnz     short loc_180010BB2
0x180010ba6  mov     rax, [r9+0FCh]
0x180010bad  sub     rax, [rcx+rbx+8]
0x180010bb2  test    rax, rax
0x180010bb5  cmovz   edx, r12d
0x180010bb9  inc     r8d
0x180010bbc  cmp     r8d, ebp
0x180010bbf  jb      short loc_180010B92
0x180010bc1  test    edx, edx
0x180010bc3  jnz     short loc_180010BEF
0x180010bc5  lea     rcx, [r10+18h]; struct sockaddr *
0x180010bc9  call    ?AddressIsLoopback@@YAHPEBUsockaddr@@@Z; AddressIsLoopback(sockaddr const *)
0x180010bce  test    eax, eax
0x180010bd0  jnz     short loc_180010BEF
0x180010bd2  movups  xmm0, xmmword ptr [r9+0F4h]
0x180010bda  mov     eax, ebp
0x180010bdc  imul    rcx, rax, 1Ch
0x180010be0  inc     ebp
0x180010be2  movups  xmmword ptr [rcx+rbx], xmm0
0x180010be6  mov     qword ptr [rcx+rbx+14h], 0
0x180010bef  cmp     rdi, r15
0x180010bf2  jnz     short loc_180010B80
0x180010bf4  lea     rcx, stru_180042240; lpCriticalSection
0x180010bfb  call    cs:__imp_LeaveCriticalSection
0x180010c01  jmp     loc_180010B16
0x180010c06  mov     [rsp+58h+arg_8], r14
0x180010c0b  xor     r14d, r14d
0x180010c0e  test    ebp, ebp
0x180010c10  jz      loc_180010C9E
0x180010c16  mov     [rsp+58h+arg_0], r13
0x180010c1b  lea     r13, WPP_GLOBAL_Control
0x180010c22  mov     rdi, cs:qword_180042230
0x180010c29  cmp     rdi, r15
0x180010c2c  jz      short loc_180010C91
0x180010c2e  mov     eax, r14d
0x180010c31  imul    rsi, rax, 1Ch
0x180010c35  add     rsi, rbx
0x180010c38  nop     dword ptr [rax+rax+00000000h]
0x180010c40  lea     r9, [rdi]
0x180010c43  mov     rdi, [rdi]
0x180010c46  mov     rax, [r9+0F4h]
0x180010c4d  sub     rax, [rsi]
0x180010c50  jnz     short loc_180010C5D
0x180010c52  mov     rax, [r9+0FCh]
0x180010c59  sub     rax, [rsi+8]
0x180010c5d  test    rax, rax
0x180010c60  jnz     short loc_180010C8C
0x180010c62  cmp     [rsi+14h], eax
0x180010c65  jz      short loc_180010CA8
0x180010c67  cmp     [rsi+18h], eax
0x180010c6a  jnz     short loc_180010CA8
0x180010c6c  mov     ecx, r12d
0x180010c6f  mov     [r9+104h], ecx
0x180010c76  mov     eax, [rsi+10h]
0x180010c79  mov     [r9+108h], eax
0x180010c80  mov     rax, cs:WPP_GLOBAL_Control
0x180010c87  cmp     rax, r13
0x180010c8a  jnz     short loc_180010CAC
0x180010c8c  cmp     rdi, r15
0x180010c8f  jnz     short loc_180010C40
0x180010c91  inc     r14d
0x180010c94  cmp     r14d, ebp
0x180010c97  jb      short loc_180010C22
0x180010c99  mov     r13, [rsp+58h+arg_0]
0x180010c9e  mov     r14, [rsp+58h+arg_8]
0x180010ca3  jmp     loc_180010B52
0x180010ca8  xor     ecx, ecx
0x180010caa  jmp     short loc_180010C6F
0x180010cac  test    dword ptr [rax+1Ch], 200h
0x180010cb3  jz      short loc_180010C8C
0x180010cb5  mov     r9, [r9+0E0h]
0x180010cbc  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180010cc3  mov     dword ptr [rsp+58h+var_38], ecx
0x180010cc7  mov     edx, 20h ; ' '
0x180010ccc  mov     rcx, [rax+10h]
0x180010cd0  call    WPP_SF_sd
0x180010cd5  jmp     short loc_180010C8C
```
