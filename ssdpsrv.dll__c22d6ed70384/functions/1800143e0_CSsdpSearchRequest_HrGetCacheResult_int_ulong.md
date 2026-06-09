# CSsdpSearchRequest::HrGetCacheResult(int,ulong *)

- ea: `0x1800143e0`
- end: `0x1800147d7`
- name: `?HrGetCacheResult@CSsdpSearchRequest@@QEAAJHPEAK@Z`
- size: `1015`
- prototype: `__int64 __fastcall(CSsdpSearchRequest *__hidden this, int, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180013924`
- `0x180013a70`

## callees

- `0x18000554c`
- `0x180006d70`
- `0x180009fd0`
- `0x1800143e0`
- `0x1800147e0`
- `0x180014868`
- `0x180014ea0`
- `0x1800255a8`
- `0x180028000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014538`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800145c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800145cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001470f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014538`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800145c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800145cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001470f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001447b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001447b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800145dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800145dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014545`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014463`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800144cc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180014463`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800144cc`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequest::HrGetCacheResult(CSsdpSearchRequest *this, int a2, unsigned int *a3)
{
  const WCHAR *v3; // r8
  unsigned int v4; // ebp
  char *v6; // r15
  __int64 v7; // rax
  int cbMultiByte; // edi
  CHAR *lpMultiByteStr; // rbx
  int v10; // esi
  LPCSTR v11; // rcx
  unsigned int v12; // r8d
  _QWORD *v13; // rdi
  int i; // esi
  int v15; // eax
  int j; // esi
  void *v17; // rcx
  unsigned int Win32Error; // eax
  struct _GUID v20; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+8h]
  void *Block; // [rsp+B8h] [rbp+20h] BYREF

  v3 = (const WCHAR *)*((_QWORD *)this + 1);
  v4 = 0;
  v6 = 0;
  Block = 0;
  v21 = 0;
  if ( !v3 )
    goto LABEL_32;
  v7 = -1;
  do
    ++v7;
  while ( v3[v7] );
  if ( v7 )
    cbMultiByte = WideCharToMultiByte(0, 0x400u, v3, -1, 0, 0, 0, 0);
  else
LABEL_32:
    cbMultiByte = 1;
  lpMultiByteStr = (CHAR *)malloc(cbMultiByte);
  if ( !lpMultiByteStr )
  {
    v11 = WPP_GLOBAL_Control;
    v4 = -2147024882;
    goto LABEL_33;
  }
  v10 = 0;
  if ( !CUString::GetLength((CSsdpSearchRequest *)((char *)this + 8)) )
  {
    *lpMultiByteStr = 0;
    v11 = WPP_GLOBAL_Control;
LABEL_11:
    v6 = lpMultiByteStr;
    if ( !v10 )
      goto LABEL_12;
    goto LABEL_33;
  }
  if ( !WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 1), -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    Win32Error = HrFromLastWin32Error();
    v10 = Win32Error;
    if ( Win32Error )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_10;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, Win32Error);
    }
  }
  v11 = WPP_GLOBAL_Control;
LABEL_10:
  v4 = v10;
  if ( v10 >= 0 )
    goto LABEL_11;
  free(lpMultiByteStr);
  v11 = WPP_GLOBAL_Control;
LABEL_33:
  if ( v11 != (LPCSTR)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v11 + 2), 15, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, v4);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( (v4 & 0x80000000) == 0 )
  {
    v12 = *((_DWORD *)this + 69);
    v20 = *(struct _GUID *)((char *)this + 280);
    v4 = CSsdpCacheEntryManager::HrSearchListCache(
           (CSsdpCacheEntryManager *)&CSsdpCacheEntryManager::s_instance,
           v6,
           v12,
           &v20,
           (struct _MessageList **)&Block);
    free(v6);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v13 = Block;
    if ( Block )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
          *(unsigned int *)Block);
      for ( i = 0; i < *(_DWORD *)v13; ++i )
      {
        if ( !a2
          || !(unsigned int)CSsdpSearchRequest::FIsInResponseMessageList(
                              this,
                              *(const char **)(*(_QWORD *)(88LL * i + v13[1] + 80) + 64LL)) )
        {
          v15 = CSsdpSearchRequest::HrAddRequestToResponseMessageList(
                  this,
                  (const struct _SSDP_REQUEST *)(v13[1] + 88LL * i));
          v4 = v15;
          if ( v15 )
          {
            if ( v15 == -2147467260 )
            {
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
              v4 = 0;
            }
            break;
          }
          ++v21;
        }
      }
      for ( j = 0; j < *(_DWORD *)v13; ++j )
        FreeSsdpRequest((struct _SSDP_REQUEST *)(v13[1] + 88LL * j));
      v17 = (void *)v13[1];
      if ( v17 )
        free(v17);
      if ( v13 )
        free(v13);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v11 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    *a3 = v21;
    v11 = WPP_GLOBAL_Control;
  }
  if ( v4 && v11 != (LPCSTR)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v11 + 2), 16, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800143e0  mov     rax, rsp
0x1800143e3  mov     [rax+18h], r8
0x1800143e7  mov     [rax+10h], edx
0x1800143ea  push    rbp
0x1800143eb  sub     rsp, 90h
0x1800143f2  mov     r8, [rcx+8]; lpWideCharStr
0x1800143f6  xor     ebp, ebp
0x1800143f8  mov     [rax-10h], rbx
0x1800143fc  mov     [rax-20h], rdi
0x180014400  mov     [rax-30h], r13
0x180014404  mov     r13, rcx
0x180014407  mov     [rax-38h], r14
0x18001440b  mov     [rax-40h], r15
0x18001440f  mov     r15d, ebp
0x180014412  mov     [rax+20h], rbp
0x180014416  mov     [rsp+98h+arg_0], ebp
0x18001441d  test    r8, r8
0x180014420  jz      loc_180014636
0x180014426  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001442d  nop     dword ptr [rax]
0x180014430  inc     rax
0x180014433  cmp     [r8+rax*2], bp
0x180014438  jnz     short loc_180014430
0x18001443a  test    rax, rax
0x18001443d  jz      loc_180014636
0x180014443  mov     [rsp+98h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x180014448  mov     edx, 400h; dwFlags
0x18001444d  mov     [rsp+98h+lpDefaultChar], rbp; lpDefaultChar
0x180014452  xor     ecx, ecx; CodePage
0x180014454  mov     [rsp+98h+cbMultiByte], ebp; cbMultiByte
0x180014458  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18001445e  mov     [rsp+98h+lpMultiByteStr], rbp; lpMultiByteStr
0x180014463  call    cs:__imp_WideCharToMultiByte
0x180014469  mov     edi, eax
0x18001446b  mov     [rsp+98h+var_18], rsi
0x180014473  movsxd  rcx, edi; Size
0x180014476  mov     [rsp+98h+var_28], r12
0x18001447b  call    cs:__imp_malloc
0x180014481  mov     rbx, rax
0x180014484  test    rax, rax
0x180014487  jz      loc_1800146F4
0x18001448d  lea     rcx, [r13+8]; this
0x180014491  mov     esi, ebp
0x180014493  call    ?GetLength@CUString@@QEBA_KXZ; CUString::GetLength(void)
0x180014498  lea     r12, WPP_GLOBAL_Control
0x18001449f  test    rax, rax
0x1800144a2  jz      loc_180014677
0x1800144a8  mov     r8, [r13+8]; lpWideCharStr
0x1800144ac  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800144b2  mov     [rsp+98h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x1800144b7  mov     edx, 400h; dwFlags
0x1800144bc  mov     [rsp+98h+lpDefaultChar], rbp; lpDefaultChar
0x1800144c1  xor     ecx, ecx; CodePage
0x1800144c3  mov     [rsp+98h+cbMultiByte], edi; cbMultiByte
0x1800144c7  mov     [rsp+98h+lpMultiByteStr], rbx; lpMultiByteStr
0x1800144cc  call    cs:__imp_WideCharToMultiByte
0x1800144d2  test    eax, eax
0x1800144d4  jz      loc_1800146AE
0x1800144da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144e1  mov     ebp, esi
0x1800144e3  test    esi, esi
0x1800144e5  js      loc_18001470C
0x1800144eb  mov     r15, rbx
0x1800144ee  test    esi, esi
0x1800144f0  jnz     loc_180014640
0x1800144f6  test    ebp, ebp
0x1800144f8  js      loc_1800145E9
0x1800144fe  movups  xmm0, xmmword ptr [r13+118h]
0x180014506  mov     r8d, [r13+114h]; unsigned int
0x18001450d  lea     rax, [rsp+98h+Block]
0x180014515  lea     r9, [rsp+98h+var_58]; struct _GUID
0x18001451a  mov     [rsp+98h+lpMultiByteStr], rax; struct _MessageList **
0x18001451f  mov     rdx, r15; char *
0x180014522  movaps  xmmword ptr [rsp+98h+var_58.Data1], xmm0
0x180014527  lea     rcx, ?s_instance@CSsdpCacheEntryManager@@0V1@A; this
0x18001452e  call    ?HrSearchListCache@CSsdpCacheEntryManager@@QEAAJPEADKU_GUID@@PEAPEAU_MessageList@@@Z; CSsdpCacheEntryManager::HrSearchListCache(char *,ulong,_GUID,_MessageList * *)
0x180014533  mov     rcx, r15; Block
0x180014536  mov     ebp, eax
0x180014538  call    cs:__imp_free
0x18001453e  lea     rcx, [r13+98h]; lpCriticalSection
0x180014545  call    cs:__imp_EnterCriticalSection
0x18001454b  mov     rdi, [rsp+98h+Block]
0x180014553  test    rdi, rdi
0x180014556  jz      short loc_1800145D5
0x180014558  mov     rcx, cs:WPP_GLOBAL_Control
0x18001455f  cmp     rcx, r12
0x180014562  jz      short loc_18001456E
0x180014564  test    byte ptr [rcx+1Ch], 8
0x180014568  jnz     loc_180014721
0x18001456e  mov     r15d, [rsp+98h+arg_8]
0x180014576  xor     esi, esi
0x180014578  cmp     esi, [rdi]
0x18001457a  jge     short loc_1800145AE
0x18001457c  movsxd  r14, esi
0x18001457f  test    r15d, r15d
0x180014582  jnz     loc_180014686
0x180014588  imul    rdx, r14, 58h ; 'X'
0x18001458c  mov     rcx, r13; this
0x18001458f  add     rdx, [rdi+8]; struct _SSDP_REQUEST *
0x180014593  call    ?HrAddRequestToResponseMessageList@CSsdpSearchRequest@@QEAAJPEBU_SSDP_REQUEST@@@Z; CSsdpSearchRequest::HrAddRequestToResponseMessageList(_SSDP_REQUEST const *)
0x180014598  mov     ebp, eax
0x18001459a  test    eax, eax
0x18001459c  jnz     loc_18001473E
0x1800145a2  inc     [rsp+98h+arg_0]
0x1800145a9  jmp     loc_1800146A7
0x1800145ae  xor     esi, esi
0x1800145b0  cmp     [rdi], esi
0x1800145b2  jg      loc_180014777
0x1800145b8  mov     rcx, [rdi+8]; Block
0x1800145bc  test    rcx, rcx
0x1800145bf  jz      short loc_1800145C7
0x1800145c1  call    cs:__imp_free
0x1800145c7  test    rdi, rdi
0x1800145ca  jz      short loc_1800145D5
0x1800145cc  mov     rcx, rdi; Block
0x1800145cf  call    cs:__imp_free
0x1800145d5  lea     rcx, [r13+98h]; lpCriticalSection
0x1800145dc  call    cs:__imp_LeaveCriticalSection
0x1800145e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145e9  mov     rax, [rsp+98h+arg_10]
0x1800145f1  mov     r15, [rsp+98h+var_40]
0x1800145f6  mov     r14, [rsp+98h+var_38]
0x1800145fb  mov     r13, [rsp+98h+var_30]
0x180014600  mov     rdi, [rsp+98h+var_20]
0x180014605  mov     rsi, [rsp+98h+var_18]
0x18001460d  mov     rbx, [rsp+98h+var_10]
0x180014615  test    rax, rax
0x180014618  jnz     loc_180014792
0x18001461e  test    ebp, ebp
0x180014620  jnz     loc_1800147A7
0x180014626  mov     r12, [rsp+98h+var_28]
0x18001462b  mov     eax, ebp
0x18001462d  add     rsp, 90h
0x180014634  pop     rbp
0x180014635  retn
0x180014636  mov     edi, 1
0x18001463b  jmp     loc_18001446B
0x180014640  cmp     rcx, r12
0x180014643  jz      loc_1800144F6
0x180014649  test    byte ptr [rcx+1Ch], 1
0x18001464d  jz      loc_1800144F6
0x180014653  mov     rcx, [rcx+10h]
0x180014657  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x18001465e  mov     edx, 0Fh
0x180014663  mov     r9d, ebp
0x180014666  call    WPP_SF_d
0x18001466b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014672  jmp     loc_1800144F6
0x180014677  mov     [rbx], sil
0x18001467a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014681  jmp     loc_1800144EB
0x180014686  mov     rax, [rdi+8]
0x18001468a  mov     rcx, r13; this
0x18001468d  imul    rdx, r14, 58h ; 'X'
0x180014691  mov     rdx, [rdx+rax+50h]
0x180014696  mov     rdx, [rdx+40h]; char *
0x18001469a  call    ?FIsInResponseMessageList@CSsdpSearchRequest@@QEAAHPEBD@Z; CSsdpSearchRequest::FIsInResponseMessageList(char const *)
0x18001469f  test    eax, eax
0x1800146a1  jz      loc_180014588
0x1800146a7  inc     esi
0x1800146a9  jmp     loc_180014578
0x1800146ae  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800146b3  mov     esi, eax
0x1800146b5  test    eax, eax
0x1800146b7  jz      loc_1800144DA
0x1800146bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c4  cmp     rcx, r12
0x1800146c7  jz      loc_1800144E1
0x1800146cd  test    byte ptr [rcx+1Ch], 1
0x1800146d1  jz      loc_1800144E1
0x1800146d7  mov     rcx, [rcx+10h]
0x1800146db  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800146e2  mov     edx, 0Eh
0x1800146e7  mov     r9d, eax
0x1800146ea  call    WPP_SF_d
0x1800146ef  jmp     loc_1800144DA
0x1800146f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146fb  lea     r12, WPP_GLOBAL_Control
0x180014702  mov     ebp, 8007000Eh
0x180014707  jmp     loc_180014640
0x18001470c  mov     rcx, rbx; Block
0x18001470f  call    cs:__imp_free
0x180014715  mov     rcx, cs:WPP_GLOBAL_Control
0x18001471c  jmp     loc_180014640
0x180014721  mov     r9d, [rdi]
0x180014724  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18001472b  mov     rcx, [rcx+10h]
0x18001472f  mov     edx, 0Eh
0x180014734  call    WPP_SF_d
0x180014739  jmp     loc_18001456E
0x18001473e  cmp     eax, 80004004h
0x180014743  jnz     loc_1800145AE
0x180014749  mov     rcx, cs:WPP_GLOBAL_Control
0x180014750  cmp     rcx, r12
0x180014753  jz      short loc_180014770
0x180014755  test    byte ptr [rcx+1Ch], 8
0x180014759  jz      short loc_180014770
0x18001475b  mov     rcx, [rcx+10h]
0x18001475f  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180014766  mov     edx, 0Fh
0x18001476b  call    WPP_SF_
0x180014770  xor     ebp, ebp
0x180014772  jmp     loc_1800145AE
0x180014777  movsxd  rax, esi
0x18001477a  imul    rcx, rax, 58h ; 'X'
0x18001477e  add     rcx, [rdi+8]; struct _SSDP_REQUEST *
0x180014782  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180014787  inc     esi
0x180014789  cmp     esi, [rdi]
0x18001478b  jl      short loc_180014777
0x18001478d  jmp     loc_1800145B8
0x180014792  mov     ecx, [rsp+98h+arg_0]
0x180014799  mov     [rax], ecx
0x18001479b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a2  jmp     loc_18001461E
0x1800147a7  cmp     rcx, r12
0x1800147aa  jz      loc_180014626
0x1800147b0  test    byte ptr [rcx+1Ch], 1
0x1800147b4  jz      loc_180014626
0x1800147ba  mov     rcx, [rcx+10h]
0x1800147be  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x1800147c5  mov     edx, 10h
0x1800147ca  mov     r9d, ebp
0x1800147cd  call    WPP_SF_d
0x1800147d2  jmp     loc_180014626
```
