# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800172c4`
- end: `0x1800175a3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `735`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800170b4`
- `0x18002f720`

## callees

- `0x1800172a8`
- `0x1800172c4`
- `0x1800175ac`
- `0x1800175d8`
- `0x18002f67c`
- `0x18002f8c0`
- `0x1800358c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800173d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800174a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800173d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800174a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017536`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rbx
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  int v33; // eax
  void *v34; // rdx
  void *v35; // rdx
  void *v36; // rdx
  void *v37; // rdx
  const char *v39; // r9
  unsigned int v40; // ebx
  int v41; // [rsp+20h] [rbp-E0h] BYREF
  int v42; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v43; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v43 = v19;
  v20 = v19;
  if ( v19 )
  {
    v42 = 0;
    v41 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v42);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      v23 = 260;
      v24 = Name;
      do
      {
        if ( !*v24 )
          break;
        ++v24;
        --v23;
      }
      while ( v23 );
      v25 = (260 - v23) & -(__int64)(v23 != 0);
      if ( v23 )
      {
        v26 = &Name[v25];
        v27 = L"h";
        v28 = 260 - v25;
        if ( 260 != v25 )
        {
          do
          {
            if ( !v5 )
              break;
            if ( !*v27 )
              break;
            *v26++ = *v27++;
            --v5;
            --v28;
          }
          while ( v28 );
        }
        v29 = v26 - 1;
        if ( v28 )
          v29 = v26;
        *v29 = 0;
      }
      v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v32 = v30;
      if ( v30 )
      {
        v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v41);
        LastError = v33;
        if ( v33 >= 0 )
        {
          wil::details::CloseHandle(v32, v34);
          *a3 = v42 | (unsigned __int64)((__int64)v41 << 31);
          wil::details::CloseHandle(v20, v37);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v33,
          v41);
        wil::details::CloseHandle(v32, v35);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
      }
      wil::details::CloseHandle(v20, v36);
      return LastError;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v41);
LABEL_40:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    return LastError;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
    goto LABEL_40;
  }
  v40 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
  return v40;
}

```

## disassembly

```asm
0x1800172c4  mov     [rsp-8+arg_0], rbx
0x1800172c9  mov     [rsp-8+arg_8], rsi
0x1800172ce  push    rbp
0x1800172cf  push    rdi
0x1800172d0  push    r12
0x1800172d2  push    r14
0x1800172d4  push    r15
0x1800172d6  lea     rbp, [rsp-150h]
0x1800172de  sub     rsp, 250h
0x1800172e5  mov     rax, cs:__security_cookie
0x1800172ec  xor     rax, rsp
0x1800172ef  mov     [rbp+170h+var_30], rax
0x1800172f6  xor     r12d, r12d
0x1800172f9  lea     rax, [rsp+270h+Name]
0x1800172fe  mov     r14d, 7FFFFFFEh
0x180017304  mov     [r8], r12
0x180017307  mov     ebx, 104h
0x18001730c  mov     r9d, r14d
0x18001730f  mov     edx, ebx
0x180017311  mov     r15, r8
0x180017314  test    r9, r9
0x180017317  jz      short loc_180017338
0x180017319  movzx   r8d, word ptr [rcx]
0x18001731d  test    r8w, r8w
0x180017321  jz      short loc_180017338
0x180017323  mov     [rax], r8w
0x180017327  add     rcx, 2
0x18001732b  add     rax, 2
0x18001732f  dec     r9
0x180017332  sub     rdx, 1
0x180017336  jnz     short loc_180017314
0x180017338  test    rdx, rdx
0x18001733b  lea     rcx, [rax-2]
0x18001733f  mov     rdx, rbx
0x180017342  cmovnz  rcx, rax
0x180017346  lea     rax, [rsp+270h+Name]
0x18001734b  mov     [rcx], r12w
0x18001734f  cmp     [rax], r12w
0x180017353  jz      short loc_18001735F
0x180017355  add     rax, 2
0x180017359  sub     rdx, 1
0x18001735d  jnz     short loc_18001734F
0x18001735f  mov     rcx, rbx
0x180017362  mov     rax, rdx
0x180017365  sub     rcx, rdx
0x180017368  neg     rax
0x18001736b  sbb     r8, r8
0x18001736e  and     r8, rcx
0x180017371  test    rdx, rdx
0x180017374  jz      short loc_1800173C4
0x180017376  mov     rax, rbx
0x180017379  lea     rdx, [rsp+270h+Name]
0x18001737e  lea     r9, aP0; "_p0"
0x180017385  mov     rcx, r14
0x180017388  lea     rdx, [rdx+r8*2]
0x18001738c  sub     rax, r8
0x18001738f  jz      short loc_1800173B5
0x180017391  test    rcx, rcx
0x180017394  jz      short loc_1800173B5
0x180017396  movzx   r8d, word ptr [r9]
0x18001739a  test    r8w, r8w
0x18001739e  jz      short loc_1800173B5
0x1800173a0  mov     [rdx], r8w
0x1800173a4  add     r9, 2
0x1800173a8  add     rdx, 2
0x1800173ac  dec     rcx
0x1800173af  sub     rax, 1
0x1800173b3  jnz     short loc_180017391
0x1800173b5  test    rax, rax
0x1800173b8  lea     rcx, [rdx-2]
0x1800173bc  cmovnz  rcx, rdx
0x1800173c0  mov     [rcx], r12w
0x1800173c4  lea     r8, [rsp+270h+Name]; lpName
0x1800173c9  xor     edx, edx; bInheritHandle
0x1800173cb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800173d0  call    cs:__imp_OpenSemaphoreW
0x1800173d6  mov     [rsp+270h+var_248], rax
0x1800173db  mov     rdi, rax
0x1800173de  test    rax, rax
0x1800173e1  jz      loc_180017536
0x1800173e7  lea     rdx, [rsp+270h+var_24C]; int *
0x1800173ec  mov     [rsp+270h+var_24C], r12d
0x1800173f1  mov     rcx, rax; hHandle
0x1800173f4  mov     [rsp+270h+var_250], r12d; int
0x1800173f9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800173fe  mov     esi, eax
0x180017400  test    eax, eax
0x180017402  jns     short loc_180017424
0x180017404  mov     rcx, [rbp+178h]; this
0x18001740b  lea     r8, aWil; "wil"
0x180017412  mov     r9d, eax; char *
0x180017415  mov     edx, 0D6h; void *
0x18001741a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001741f  jmp     loc_180017544
0x180017424  mov     rdx, rbx
0x180017427  lea     rax, [rsp+270h+Name]
0x18001742c  cmp     [rax], r12w
0x180017430  jz      short loc_18001743C
0x180017432  add     rax, 2
0x180017436  sub     rdx, 1
0x18001743a  jnz     short loc_18001742C
0x18001743c  mov     rcx, rbx
0x18001743f  mov     rax, rdx
0x180017442  sub     rcx, rdx
0x180017445  neg     rax
0x180017448  sbb     r8, r8
0x18001744b  and     r8, rcx
0x18001744e  test    rdx, rdx
0x180017451  jz      short loc_180017498
0x180017453  lea     rax, [rsp+270h+Name]
0x180017458  lea     rax, [rax+r8*2]
0x18001745c  lea     rcx, asc_180073348; "h"
0x180017463  sub     rbx, r8
0x180017466  jz      short loc_180017489
0x180017468  test    r14, r14
0x18001746b  jz      short loc_180017489
0x18001746d  movzx   edx, word ptr [rcx]
0x180017470  test    dx, dx
0x180017473  jz      short loc_180017489
0x180017475  mov     [rax], dx
0x180017478  add     rcx, 2
0x18001747c  add     rax, 2
0x180017480  dec     r14
0x180017483  sub     rbx, 1
0x180017487  jnz     short loc_180017468
0x180017489  test    rbx, rbx
0x18001748c  lea     rdx, [rax-2]
0x180017490  cmovnz  rdx, rax
0x180017494  mov     [rdx], r12w
0x180017498  lea     r8, [rsp+270h+Name]; lpName
0x18001749d  xor     edx, edx; bInheritHandle
0x18001749f  mov     ecx, 1F0003h; dwDesiredAccess
0x1800174a4  call    cs:__imp_OpenSemaphoreW
0x1800174aa  mov     rbx, rax
0x1800174ad  test    rax, rax
0x1800174b0  jz      short loc_180017512
0x1800174b2  lea     rdx, [rsp+270h+var_250]; int *
0x1800174b7  mov     rcx, rax; hHandle
0x1800174ba  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800174bf  mov     esi, eax
0x1800174c1  test    eax, eax
0x1800174c3  jns     short loc_1800174EA
0x1800174c5  mov     rcx, [rbp+178h]; this
0x1800174cc  lea     r8, aWil; "wil"
0x1800174d3  mov     r9d, eax; char *
0x1800174d6  mov     edx, 0DEh; void *
0x1800174db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174e0  mov     rcx, rbx; this
0x1800174e3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800174e8  jmp     short loc_18001752C
0x1800174ea  mov     rcx, rbx; this
0x1800174ed  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800174f2  movsxd  rax, [rsp+270h+var_24C]
0x1800174f7  movsxd  rcx, [rsp+270h+var_250]
0x1800174fc  shl     rcx, 1Fh
0x180017500  or      rcx, rax
0x180017503  mov     [r15], rcx
0x180017506  mov     rcx, rdi; this
0x180017509  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001750e  xor     eax, eax
0x180017510  jmp     short loc_180017578
0x180017512  mov     rcx, [rbp+178h]; this
0x180017519  lea     r8, aWil; "wil"
0x180017520  mov     edx, 0DCh; void *
0x180017525  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001752a  mov     esi, eax
0x18001752c  mov     rcx, rdi; this
0x18001752f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180017534  jmp     short loc_18001754E
0x180017536  call    cs:__imp_GetLastError
0x18001753c  cmp     eax, 2
0x18001753f  jnz     short loc_180017552
0x180017541  mov     esi, r12d
0x180017544  lea     rcx, [rsp+270h+var_248]
0x180017549  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001754e  mov     eax, esi
0x180017550  jmp     short loc_180017578
0x180017552  mov     rcx, [rbp+178h]; this
0x180017559  lea     r8, aWil; "wil"
0x180017560  mov     edx, 0D0h; void *
0x180017565  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001756a  lea     rcx, [rsp+270h+var_248]
0x18001756f  mov     ebx, eax
0x180017571  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017576  mov     eax, ebx
0x180017578  mov     rcx, [rbp+170h+var_30]
0x18001757f  xor     rcx, rsp; StackCookie
0x180017582  call    __security_check_cookie
0x180017587  lea     r11, [rsp+270h+var_20]
0x18001758f  mov     rbx, [r11+30h]
0x180017593  mov     rsi, [r11+38h]
0x180017597  mov     rsp, r11
0x18001759a  pop     r15
0x18001759c  pop     r14
0x18001759e  pop     r12
0x1800175a0  pop     rdi
0x1800175a1  pop     rbp
0x1800175a2  retn
```
