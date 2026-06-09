# UpdateFirewallAllowedOnNetworkAddressList(void)

- ea: `0x180011f30`
- end: `0x1800121a7`
- name: `?UpdateFirewallAllowedOnNetworkAddressList@@YAXXZ`
- size: `631`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180010390`
- `0x180011d00`

## callees

- `0x180011ec0`
- `0x180011f30`
- `0x1800121b0`
- `0x18002e8f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012011`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012011`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011f83`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012002`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800120bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012002`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800120bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fe3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fe3`

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
  EnterCriticalSection(&stru_180045330);
  v2 = qword_180045320;
  v3 = dword_180045710;
  for ( i = qword_180045320; i != (struct _SSDPNetwork *)&qword_180045320; ++v0 )
    i = *(struct _SSDPNetwork **)i;
  v5 = (struct AllowedInterface *)malloc(28LL * v0);
  if ( !v5 || v2 == (struct _SSDPNetwork *)&qword_180045320 )
  {
    LeaveCriticalSection(&stru_180045330);
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
    while ( v2 != (struct _SSDPNetwork *)&qword_180045320 );
    LeaveCriticalSection(&stru_180045330);
  }
  if ( !(unsigned int)CFirewallManager::CheckAllowedInterfaces(
                        (CFirewallManager *)&CFirewallManager::s_instance,
                        1900,
                        17,
                        v1,
                        v5) )
  {
    EnterCriticalSection(&stru_180045330);
    if ( v3 == dword_180045710 )
    {
      for ( j = 0; j < v1; ++j )
      {
        v15 = qword_180045320;
        if ( qword_180045320 != (struct _SSDPNetwork *)&qword_180045320 )
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
          while ( v15 != (struct _SSDPNetwork *)&qword_180045320 );
        }
      }
    }
    LeaveCriticalSection(&stru_180045330);
  }
  free(v5);
}

```

## disassembly

```asm
0x180011f30  mov     [rsp+arg_10], rbx
0x180011f35  push    rbp
0x180011f36  push    rsi
0x180011f37  push    rdi
0x180011f38  push    r12
0x180011f3a  push    r15
0x180011f3c  sub     rsp, 30h
0x180011f40  lea     rcx, stru_180045330; lpCriticalSection
0x180011f47  xor     ebx, ebx
0x180011f49  xor     ebp, ebp
0x180011f4b  call    cs:__imp_EnterCriticalSection
0x180011f52  nop     dword ptr [rax+rax+00h]
0x180011f57  mov     rdi, cs:qword_180045320
0x180011f5e  lea     r15, qword_180045320
0x180011f65  mov     esi, cs:dword_180045710
0x180011f6b  mov     rax, rdi
0x180011f6e  cmp     rdi, r15
0x180011f71  jz      short loc_180011F7D
0x180011f73  mov     rax, [rax]
0x180011f76  inc     ebx
0x180011f78  cmp     rax, r15
0x180011f7b  jnz     short loc_180011F73
0x180011f7d  mov     eax, ebx
0x180011f7f  imul    rcx, rax, 1Ch; Size
0x180011f83  call    cs:__imp_malloc
0x180011f8a  nop     dword ptr [rax+rax+00h]
0x180011f8f  mov     rbx, rax
0x180011f92  mov     r12d, 1
0x180011f98  test    rax, rax
0x180011f9b  jnz     loc_18001202F
0x180011fa1  lea     rcx, stru_180045330; lpCriticalSection
0x180011fa8  call    cs:__imp_LeaveCriticalSection
0x180011faf  nop     dword ptr [rax+rax+00h]
0x180011fb4  test    rbx, rbx
0x180011fb7  jz      short loc_18001201D
0x180011fb9  mov     edx, 76Ch; unsigned __int16
0x180011fbe  mov     [rsp+58h+var_38], rbx; struct AllowedInterface *
0x180011fc3  mov     r8d, 11h; unsigned __int16
0x180011fc9  lea     rcx, ?s_instance@CFirewallManager@@0V1@A; this
0x180011fd0  mov     r9d, ebp; unsigned int
0x180011fd3  call    ?CheckAllowedInterfaces@CFirewallManager@@AEAAKGGKPEAUAllowedInterface@@@Z; CFirewallManager::CheckAllowedInterfaces(ushort,ushort,ulong,AllowedInterface *)
0x180011fd8  test    eax, eax
0x180011fda  jnz     short loc_18001200E
0x180011fdc  lea     rcx, stru_180045330; lpCriticalSection
0x180011fe3  call    cs:__imp_EnterCriticalSection
0x180011fea  nop     dword ptr [rax+rax+00h]
0x180011fef  cmp     esi, cs:dword_180045710
0x180011ff5  jz      loc_1800120CC
0x180011ffb  lea     rcx, stru_180045330; lpCriticalSection
0x180012002  call    cs:__imp_LeaveCriticalSection
0x180012009  nop     dword ptr [rax+rax+00h]
0x18001200e  mov     rcx, rbx; Block
0x180012011  call    cs:__imp_free
0x180012018  nop     dword ptr [rax+rax+00h]
0x18001201d  mov     rbx, [rsp+58h+arg_10]
0x180012022  add     rsp, 30h
0x180012026  pop     r15
0x180012028  pop     r12
0x18001202a  pop     rdi
0x18001202b  pop     rsi
0x18001202c  pop     rbp
0x18001202d  retn
0x18001202f  cmp     rdi, r15
0x180012032  jz      loc_180011FA1
0x180012038  nop     dword ptr [rax+rax+00000000h]
0x180012040  xor     edx, edx
0x180012042  xor     r8d, r8d
0x180012045  mov     r10, rdi
0x180012048  mov     r9, rdi
0x18001204b  mov     rdi, [rdi]
0x18001204e  test    ebp, ebp
0x180012050  jz      short loc_180012085
0x180012052  mov     eax, r8d
0x180012055  imul    rcx, rax, 1Ch
0x180012059  mov     rax, [r9+0F4h]
0x180012060  sub     rax, [rcx+rbx]
0x180012064  jnz     short loc_180012072
0x180012066  mov     rax, [r9+0FCh]
0x18001206d  sub     rax, [rcx+rbx+8]
0x180012072  test    rax, rax
0x180012075  cmovz   edx, r12d
0x180012079  inc     r8d
0x18001207c  cmp     r8d, ebp
0x18001207f  jb      short loc_180012052
0x180012081  test    edx, edx
0x180012083  jnz     short loc_1800120AF
0x180012085  lea     rcx, [r10+18h]; struct sockaddr *
0x180012089  call    ?AddressIsLoopback@@YAHPEBUsockaddr@@@Z; AddressIsLoopback(sockaddr const *)
0x18001208e  test    eax, eax
0x180012090  jnz     short loc_1800120AF
0x180012092  movups  xmm0, xmmword ptr [r9+0F4h]
0x18001209a  mov     eax, ebp
0x18001209c  imul    rcx, rax, 1Ch
0x1800120a0  inc     ebp
0x1800120a2  movups  xmmword ptr [rcx+rbx], xmm0
0x1800120a6  mov     qword ptr [rcx+rbx+14h], 0
0x1800120af  cmp     rdi, r15
0x1800120b2  jnz     short loc_180012040
0x1800120b4  lea     rcx, stru_180045330; lpCriticalSection
0x1800120bb  call    cs:__imp_LeaveCriticalSection
0x1800120c2  nop     dword ptr [rax+rax+00h]
0x1800120c7  jmp     loc_180011FB9
0x1800120cc  mov     [rsp+58h+arg_8], r14
0x1800120d1  xor     r14d, r14d
0x1800120d4  test    ebp, ebp
0x1800120d6  jz      loc_18001216E
0x1800120dc  mov     [rsp+58h+arg_0], r13
0x1800120e1  lea     r13, WPP_GLOBAL_Control
0x1800120e8  nop     dword ptr [rax+rax+00000000h]
0x1800120f0  mov     rdi, cs:qword_180045320
0x1800120f7  cmp     rdi, r15
0x1800120fa  jz      short loc_180012161
0x1800120fc  mov     eax, r14d
0x1800120ff  imul    rsi, rax, 1Ch
0x180012103  add     rsi, rbx
0x180012106  nop     word ptr [rax+rax+00000000h]
0x180012110  lea     r9, [rdi]
0x180012113  mov     rdi, [rdi]
0x180012116  mov     rax, [r9+0F4h]
0x18001211d  sub     rax, [rsi]
0x180012120  jnz     short loc_18001212D
0x180012122  mov     rax, [r9+0FCh]
0x180012129  sub     rax, [rsi+8]
0x18001212d  test    rax, rax
0x180012130  jnz     short loc_18001215C
0x180012132  cmp     [rsi+14h], eax
0x180012135  jz      short loc_180012178
0x180012137  cmp     [rsi+18h], eax
0x18001213a  jnz     short loc_180012178
0x18001213c  mov     ecx, r12d
0x18001213f  mov     [r9+104h], ecx
0x180012146  mov     eax, [rsi+10h]
0x180012149  mov     [r9+108h], eax
0x180012150  mov     rax, cs:WPP_GLOBAL_Control
0x180012157  cmp     rax, r13
0x18001215a  jnz     short loc_18001217C
0x18001215c  cmp     rdi, r15
0x18001215f  jnz     short loc_180012110
0x180012161  inc     r14d
0x180012164  cmp     r14d, ebp
0x180012167  jb      short loc_1800120F0
0x180012169  mov     r13, [rsp+58h+arg_0]
0x18001216e  mov     r14, [rsp+58h+arg_8]
0x180012173  jmp     loc_180011FFB
0x180012178  xor     ecx, ecx
0x18001217a  jmp     short loc_18001213F
0x18001217c  test    dword ptr [rax+1Ch], 200h
0x180012183  jz      short loc_18001215C
0x180012185  mov     r9, [r9+0E0h]
0x18001218c  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180012193  mov     dword ptr [rsp+58h+var_38], ecx
0x180012197  mov     edx, 20h ; ' '
0x18001219c  mov     rcx, [rax+10h]
0x1800121a0  call    WPP_SF_sd
0x1800121a5  jmp     short loc_18001215C
```
