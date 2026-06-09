# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180034fec`
- end: `0x1800352c6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `730`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180034c98`
- `0x180034d54`

## callees

- `0x180034fec`
- `0x1800352cc`
- `0x180035454`
- `0x180035484`
- `0x180043820`
- `0x180043ac8`
- `0x180079490`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800350f8`
- `KERNEL32!OpenSemaphoreW` at `0x180035204`
- `KERNEL32!OpenSemaphoreW` at `0x1800350f8`
- `KERNEL32!OpenSemaphoreW` at `0x180035204`
- `KERNEL32!GetLastError` at `0x180035111`
- `KERNEL32!GetLastError` at `0x180035111`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  int ValueFromSemaphore; // eax
  unsigned int v25; // r8d
  unsigned int LastError; // ebx
  __int64 v27; // rdx
  WCHAR *v28; // rax
  __int64 v29; // r8
  WCHAR *v30; // rax
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rsi
  WCHAR *v33; // rdx
  wil::details *v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  wil::details *v37; // rbx
  int v38; // eax
  void *v39; // rdx
  unsigned int v40; // r8d
  int v41; // esi
  void *v42; // rdx
  int v43; // [rsp+20h] [rbp-E0h] BYREF
  int v44; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v45; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v46; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

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
  v46 = v19;
  v20 = v19;
  if ( v19 )
  {
    v44 = 0;
    v43 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v44);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v25, (const char *)(unsigned int)ValueFromSemaphore, v43);
    }
    else
    {
      v27 = 260;
      v28 = Name;
      do
      {
        if ( !*v28 )
          break;
        ++v28;
        --v27;
      }
      while ( v27 );
      v29 = (260 - v27) & -(__int64)(v27 != 0);
      if ( v27 )
      {
        v30 = &Name[v29];
        v31 = L"h";
        v32 = 260 - v29;
        if ( 260 != v29 )
        {
          do
          {
            if ( !v5 )
              break;
            if ( !*v31 )
              break;
            *v30++ = *v31++;
            --v5;
            --v32;
          }
          while ( v32 );
        }
        v33 = v30 - 1;
        if ( v32 )
          v33 = v30;
        *v33 = 0;
      }
      v34 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v45 = v34;
      v37 = v34;
      if ( v34 )
      {
        v38 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v34, &v43);
        v41 = v38;
        if ( v38 >= 0 )
        {
          wil::details::CloseHandle(v37, v39);
          *a3 = v44 | (unsigned __int64)((__int64)v43 << 31);
          wil::details::CloseHandle(v20, v42);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v40, (const char *)(unsigned int)v38, v43);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v45);
        LastError = v41;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v35, v36);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v45);
      }
    }
  }
  else
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v21, v22);
    LastError = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v46);
  return LastError;
}

```

## disassembly

```asm
0x180034fec  mov     [rsp-8+arg_0], rbx
0x180034ff1  mov     [rsp-8+arg_8], rsi
0x180034ff6  push    rbp
0x180034ff7  push    rdi
0x180034ff8  push    r12
0x180034ffa  push    r14
0x180034ffc  push    r15
0x180034ffe  lea     rbp, [rsp-160h]
0x180035006  sub     rsp, 260h
0x18003500d  mov     rax, cs:__security_cookie
0x180035014  xor     rax, rsp
0x180035017  mov     [rbp+180h+var_30], rax
0x18003501e  xor     r12d, r12d
0x180035021  lea     rax, [rsp+280h+Name]
0x180035026  mov     r14d, 7FFFFFFEh
0x18003502c  mov     [r8], r12
0x18003502f  mov     esi, 104h
0x180035034  mov     r9d, r14d
0x180035037  mov     edx, esi
0x180035039  mov     r15, r8
0x18003503c  test    r9, r9
0x18003503f  jz      short loc_180035060
0x180035041  movzx   r8d, word ptr [rcx]
0x180035045  test    r8w, r8w
0x180035049  jz      short loc_180035060
0x18003504b  mov     [rax], r8w
0x18003504f  add     rcx, 2
0x180035053  add     rax, 2
0x180035057  dec     r9
0x18003505a  sub     rdx, 1
0x18003505e  jnz     short loc_18003503C
0x180035060  test    rdx, rdx
0x180035063  lea     rcx, [rax-2]
0x180035067  mov     rdx, rsi
0x18003506a  cmovnz  rcx, rax
0x18003506e  lea     rax, [rsp+280h+Name]
0x180035073  mov     [rcx], r12w
0x180035077  cmp     [rax], r12w
0x18003507b  jz      short loc_180035087
0x18003507d  add     rax, 2
0x180035081  sub     rdx, 1
0x180035085  jnz     short loc_180035077
0x180035087  mov     rcx, rsi
0x18003508a  mov     rax, rdx
0x18003508d  sub     rcx, rdx
0x180035090  neg     rax
0x180035093  sbb     r8, r8
0x180035096  and     r8, rcx
0x180035099  test    rdx, rdx
0x18003509c  jz      short loc_1800350EC
0x18003509e  mov     rax, rsi
0x1800350a1  lea     rdx, [rsp+280h+Name]
0x1800350a6  lea     r9, aP0; "_p0"
0x1800350ad  mov     rcx, r14
0x1800350b0  lea     rdx, [rdx+r8*2]
0x1800350b4  sub     rax, r8
0x1800350b7  jz      short loc_1800350DD
0x1800350b9  test    rcx, rcx
0x1800350bc  jz      short loc_1800350DD
0x1800350be  movzx   r8d, word ptr [r9]
0x1800350c2  test    r8w, r8w
0x1800350c6  jz      short loc_1800350DD
0x1800350c8  mov     [rdx], r8w
0x1800350cc  add     r9, 2
0x1800350d0  add     rdx, 2
0x1800350d4  dec     rcx
0x1800350d7  sub     rax, 1
0x1800350db  jnz     short loc_1800350B9
0x1800350dd  test    rax, rax
0x1800350e0  lea     rcx, [rdx-2]
0x1800350e4  cmovnz  rcx, rdx
0x1800350e8  mov     [rcx], r12w
0x1800350ec  lea     r8, [rsp+280h+Name]; lpName
0x1800350f1  xor     edx, edx; bInheritHandle
0x1800350f3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800350f8  call    cs:__imp_OpenSemaphoreW
0x1800350ff  nop     dword ptr [rax+rax+00h]
0x180035104  mov     [rsp+280h+var_250], rax
0x180035109  mov     rdi, rax
0x18003510c  test    rax, rax
0x18003510f  jnz     short loc_180035163
0x180035111  call    cs:__imp_GetLastError
0x180035118  nop     dword ptr [rax+rax+00h]
0x18003511d  cmp     eax, 2
0x180035120  jz      loc_1800352C1
0x180035126  mov     rcx, [rbp+188h]; this
0x18003512d  mov     edx, 0D0h; void *
0x180035132  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035137  mov     rcx, [rbp+180h+var_30]
0x18003513e  xor     rcx, rsp; StackCookie
0x180035141  call    __security_check_cookie
0x180035146  lea     r11, [rsp+280h+var_20]
0x18003514e  mov     rbx, [r11+30h]
0x180035152  mov     rsi, [r11+38h]
0x180035156  mov     rsp, r11
0x180035159  pop     r15
0x18003515b  pop     r14
0x18003515d  pop     r12
0x18003515f  pop     rdi
0x180035160  pop     rbp
0x180035161  retn
0x180035163  lea     rdx, [rsp+280h+var_25C]; int *
0x180035168  mov     [rsp+280h+var_25C], r12d
0x18003516d  mov     rcx, rdi; hHandle
0x180035170  mov     [rsp+280h+var_260], r12d; int
0x180035175  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003517a  mov     ebx, eax
0x18003517c  test    eax, eax
0x18003517e  js      loc_180035289
0x180035184  mov     rdx, rsi
0x180035187  lea     rax, [rsp+280h+Name]
0x18003518c  cmp     [rax], r12w
0x180035190  jz      short loc_18003519C
0x180035192  add     rax, 2
0x180035196  sub     rdx, 1
0x18003519a  jnz     short loc_18003518C
0x18003519c  mov     rcx, rsi
0x18003519f  mov     rax, rdx
0x1800351a2  sub     rcx, rdx
0x1800351a5  neg     rax
0x1800351a8  sbb     r8, r8
0x1800351ab  and     r8, rcx
0x1800351ae  test    rdx, rdx
0x1800351b1  jz      short loc_1800351F8
0x1800351b3  lea     rax, [rsp+280h+Name]
0x1800351b8  lea     rax, [rax+r8*2]
0x1800351bc  lea     rcx, asc_180080D78; "h"
0x1800351c3  sub     rsi, r8
0x1800351c6  jz      short loc_1800351E9
0x1800351c8  test    r14, r14
0x1800351cb  jz      short loc_1800351E9
0x1800351cd  movzx   edx, word ptr [rcx]
0x1800351d0  test    dx, dx
0x1800351d3  jz      short loc_1800351E9
0x1800351d5  mov     [rax], dx
0x1800351d8  add     rcx, 2
0x1800351dc  add     rax, 2
0x1800351e0  dec     r14
0x1800351e3  sub     rsi, 1
0x1800351e7  jnz     short loc_1800351C8
0x1800351e9  test    rsi, rsi
0x1800351ec  lea     rdx, [rax-2]
0x1800351f0  cmovnz  rdx, rax
0x1800351f4  mov     [rdx], r12w
0x1800351f8  lea     r8, [rsp+280h+Name]; lpName
0x1800351fd  xor     edx, edx; bInheritHandle
0x1800351ff  mov     ecx, 1F0003h; dwDesiredAccess
0x180035204  call    cs:__imp_OpenSemaphoreW
0x18003520b  nop     dword ptr [rax+rax+00h]
0x180035210  mov     [rsp+280h+var_258], rax
0x180035215  mov     rbx, rax
0x180035218  test    rax, rax
0x18003521b  jz      short loc_18003525B
0x18003521d  lea     rdx, [rsp+280h+var_260]; int *
0x180035222  mov     rcx, rax; hHandle
0x180035225  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003522a  mov     esi, eax
0x18003522c  test    eax, eax
0x18003522e  js      short loc_18003529F
0x180035230  mov     rcx, rbx; this
0x180035233  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180035238  movsxd  rax, [rsp+280h+var_25C]
0x18003523d  movsxd  rcx, [rsp+280h+var_260]
0x180035242  shl     rcx, 1Fh
0x180035246  or      rcx, rax
0x180035249  mov     [r15], rcx
0x18003524c  mov     rcx, rdi; this
0x18003524f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180035254  xor     eax, eax
0x180035256  jmp     loc_180035137
0x18003525b  mov     rcx, [rbp+188h]; this
0x180035262  mov     edx, 0DCh; void *
0x180035267  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003526c  lea     rcx, [rsp+280h+var_258]
0x180035271  mov     ebx, eax
0x180035273  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035278  lea     rcx, [rsp+280h+var_250]
0x18003527d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035282  mov     eax, ebx
0x180035284  jmp     loc_180035137
0x180035289  mov     rcx, [rbp+188h]; this
0x180035290  mov     r9d, eax; char *
0x180035293  mov     edx, 0D6h; void *
0x180035298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003529d  jmp     short loc_180035278
0x18003529f  mov     rcx, [rbp+188h]; this
0x1800352a6  mov     r9d, esi; char *
0x1800352a9  mov     edx, 0DEh; void *
0x1800352ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800352b3  lea     rcx, [rsp+280h+var_258]
0x1800352b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800352bd  mov     ebx, esi
0x1800352bf  jmp     short loc_180035278
0x1800352c1  mov     ebx, r12d
0x1800352c4  jmp     short loc_180035278
```
