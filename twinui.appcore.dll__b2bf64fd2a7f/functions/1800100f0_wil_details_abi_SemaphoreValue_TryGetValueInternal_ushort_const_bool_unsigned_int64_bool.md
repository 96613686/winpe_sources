# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800100f0`
- end: `0x180010415`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `805`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000fec4`
- `0x18001cbb4`

## callees

- `0x1800100f0`
- `0x180010420`
- `0x1800105b8`
- `0x18001cc38`
- `0x18001e340`
- `0x18002b1b0`
- `0x180032714`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800101e8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800102f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800101e8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800102f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001038d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001038d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // r9
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // r10
  WCHAR *v9; // rcx
  WCHAR *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r9
  __int64 v14; // rcx
  WCHAR *v15; // r8
  __int64 v16; // rax
  WCHAR *v17; // rcx
  HANDLE v18; // rax
  void *v19; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  __int64 v25; // rdx
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rsi
  WCHAR *v29; // rdx
  HANDLE v30; // rax
  const char *v31; // r9
  void *v32; // rbx
  int v33; // eax
  unsigned int v34; // esi
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-258h] BYREF
  int v41; // [rsp+24h] [rbp-254h] BYREF
  HANDLE v42; // [rsp+28h] [rbp-250h] BYREF
  _QWORD v43[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

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
  v9 = v4 - 1;
  v10 = Name;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  v11 = 260;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v12 = 260 - v11;
  if ( v11 )
  {
    v13 = L"_p0";
    v14 = 2147483646;
    v15 = &Name[v12];
    v16 = 260 - v12;
    if ( v12 != 260 )
    {
      do
      {
        if ( !v14 )
          break;
        if ( !*v13 )
          break;
        *v15++ = *v13++;
        --v14;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v18;
  v19 = v18;
  if ( v18 )
  {
    v41 = 0;
    v40 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v41);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v40);
LABEL_21:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      return LastError;
    }
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
    v25 = 260 - v23;
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
    v30 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v43[0] = v30;
    v32 = v30;
    if ( !v30 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v43);
      goto LABEL_21;
    }
    v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
    v34 = v33;
    if ( v33 >= 0 )
    {
      if ( !CloseHandle(v32) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v33,
        v40);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v43);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      return v34;
    }
  }
  else if ( GetLastError() == 2 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
  }
}

```

## disassembly

```asm
0x1800100f0  mov     [rsp+arg_8], rbp
0x1800100f5  mov     [rsp+arg_18], rsi
0x1800100fa  push    rdi
0x1800100fb  push    r14
0x1800100fd  push    r15
0x1800100ff  sub     rsp, 260h
0x180010106  mov     rax, cs:__security_cookie
0x18001010d  xor     rax, rsp
0x180010110  mov     [rsp+278h+var_28], rax
0x180010118  xor     r15d, r15d
0x18001011b  lea     r9, [rsp+278h+Name]
0x180010120  mov     ebp, 7FFFFFFEh
0x180010125  mov     [r8], r15
0x180010128  mov     esi, 104h
0x18001012d  mov     edx, ebp
0x18001012f  mov     r10d, esi
0x180010132  mov     r14, r8
0x180010135  test    rdx, rdx
0x180010138  jz      short loc_180010157
0x18001013a  movzx   eax, word ptr [rcx]
0x18001013d  test    ax, ax
0x180010140  jz      short loc_180010157
0x180010142  mov     [r9], ax
0x180010146  add     rcx, 2
0x18001014a  add     r9, 2
0x18001014e  dec     rdx
0x180010151  sub     r10, 1
0x180010155  jnz     short loc_180010135
0x180010157  test    r10, r10
0x18001015a  lea     rcx, [r9-2]
0x18001015e  lea     rax, [rsp+278h+Name]
0x180010163  cmovnz  rcx, r9
0x180010167  mov     [rcx], r15w
0x18001016b  mov     rcx, rsi
0x18001016e  xchg    ax, ax
0x180010170  cmp     [rax], r15w
0x180010174  jz      short loc_180010180
0x180010176  add     rax, 2
0x18001017a  sub     rcx, 1
0x18001017e  jnz     short loc_180010170
0x180010180  mov     rdx, rsi
0x180010183  sub     rdx, rcx
0x180010186  test    rcx, rcx
0x180010189  cmovz   rdx, r15
0x18001018d  jz      short loc_1800101DC
0x18001018f  mov     rax, rsi
0x180010192  lea     r8, [rsp+278h+Name]
0x180010197  lea     r9, aP0; "_p0"
0x18001019e  mov     rcx, rbp
0x1800101a1  lea     r8, [r8+rdx*2]
0x1800101a5  sub     rax, rdx
0x1800101a8  jz      short loc_1800101CD
0x1800101aa  test    rcx, rcx
0x1800101ad  jz      short loc_1800101CD
0x1800101af  movzx   edx, word ptr [r9]
0x1800101b3  test    dx, dx
0x1800101b6  jz      short loc_1800101CD
0x1800101b8  mov     [r8], dx
0x1800101bc  add     r9, 2
0x1800101c0  add     r8, 2
0x1800101c4  dec     rcx
0x1800101c7  sub     rax, 1
0x1800101cb  jnz     short loc_1800101AA
0x1800101cd  test    rax, rax
0x1800101d0  lea     rcx, [r8-2]
0x1800101d4  cmovnz  rcx, r8
0x1800101d8  mov     [rcx], r15w
0x1800101dc  lea     r8, [rsp+278h+Name]; lpName
0x1800101e1  xor     edx, edx; bInheritHandle
0x1800101e3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800101e8  call    cs:__imp_OpenSemaphoreW
0x1800101ee  mov     [rsp+278h+var_250], rax
0x1800101f3  mov     rdi, rax
0x1800101f6  test    rax, rax
0x1800101f9  jz      loc_1800103DB
0x1800101ff  lea     rdx, [rsp+278h+var_254]; int *
0x180010204  mov     [rsp+278h+arg_0], rbx
0x18001020c  mov     rcx, rax; hHandle
0x18001020f  mov     [rsp+278h+var_254], r15d
0x180010214  mov     [rsp+278h+var_258], r15d; int
0x180010219  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001021e  mov     ebx, eax
0x180010220  test    eax, eax
0x180010222  jns     short loc_18001027D
0x180010224  mov     rcx, [rsp+278h]; this
0x18001022c  lea     r8, aWil; "wil"
0x180010233  mov     r9d, eax; char *
0x180010236  mov     edx, 0D6h; void *
0x18001023b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010240  lea     rcx, [rsp+278h+var_250]
0x180010245  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001024a  mov     eax, ebx
0x18001024c  mov     rbx, [rsp+278h+arg_0]
0x180010254  mov     rcx, [rsp+278h+var_28]
0x18001025c  xor     rcx, rsp; StackCookie
0x18001025f  call    __security_check_cookie
0x180010264  lea     r11, [rsp+278h+var_18]
0x18001026c  mov     rbp, [r11+28h]
0x180010270  mov     rsi, [r11+38h]
0x180010274  mov     rsp, r11
0x180010277  pop     r15
0x180010279  pop     r14
0x18001027b  pop     rdi
0x18001027c  retn
0x18001027d  mov     rcx, rsi
0x180010280  lea     rax, [rsp+278h+Name]
0x180010285  cmp     [rax], r15w
0x180010289  jz      short loc_180010295
0x18001028b  add     rax, 2
0x18001028f  sub     rcx, 1
0x180010293  jnz     short loc_180010285
0x180010295  mov     rdx, rsi
0x180010298  sub     rdx, rcx
0x18001029b  test    rcx, rcx
0x18001029e  cmovz   rdx, r15
0x1800102a2  jz      short loc_1800102E9
0x1800102a4  lea     rax, [rsp+278h+Name]
0x1800102a9  lea     rax, [rax+rdx*2]
0x1800102ad  lea     rcx, asc_180093CE0; "h"
0x1800102b4  sub     rsi, rdx
0x1800102b7  jz      short loc_1800102DA
0x1800102b9  test    rbp, rbp
0x1800102bc  jz      short loc_1800102DA
0x1800102be  movzx   edx, word ptr [rcx]
0x1800102c1  test    dx, dx
0x1800102c4  jz      short loc_1800102DA
0x1800102c6  mov     [rax], dx
0x1800102c9  add     rcx, 2
0x1800102cd  add     rax, 2
0x1800102d1  dec     rbp
0x1800102d4  sub     rsi, 1
0x1800102d8  jnz     short loc_1800102B9
0x1800102da  test    rsi, rsi
0x1800102dd  lea     rdx, [rax-2]
0x1800102e1  cmovnz  rdx, rax
0x1800102e5  mov     [rdx], r15w
0x1800102e9  lea     r8, [rsp+278h+Name]; lpName
0x1800102ee  xor     edx, edx; bInheritHandle
0x1800102f0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800102f5  call    cs:__imp_OpenSemaphoreW
0x1800102fb  mov     [rsp+278h+var_248], rax
0x180010300  mov     rbx, rax
0x180010303  test    rax, rax
0x180010306  jz      loc_1800103B1
0x18001030c  lea     rdx, [rsp+278h+var_258]; int *
0x180010311  mov     rcx, rax; hHandle
0x180010314  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010319  mov     esi, eax
0x18001031b  test    eax, eax
0x18001031d  jns     short loc_180010356
0x18001031f  mov     rcx, [rsp+278h]; this
0x180010327  lea     r8, aWil; "wil"
0x18001032e  mov     r9d, eax; char *
0x180010331  mov     edx, 0DEh; void *
0x180010336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001033b  lea     rcx, [rsp+278h+var_248]
0x180010340  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010345  lea     rcx, [rsp+278h+var_250]
0x18001034a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001034f  mov     eax, esi
0x180010351  jmp     loc_18001024C
0x180010356  mov     rcx, rbx; hObject
0x180010359  call    cs:__imp_CloseHandle
0x18001035f  test    eax, eax
0x180010361  jnz     short loc_180010376
0x180010363  mov     rcx, [rsp+278h]; this
0x18001036b  mov     edx, 0A0Bh; void *
0x180010370  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010376  movsxd  rax, [rsp+278h+var_254]
0x18001037b  movsxd  rcx, [rsp+278h+var_258]
0x180010380  shl     rcx, 1Fh
0x180010384  or      rcx, rax
0x180010387  mov     [r14], rcx
0x18001038a  mov     rcx, rdi; hObject
0x18001038d  call    cs:__imp_CloseHandle
0x180010393  test    eax, eax
0x180010395  jnz     short loc_1800103AA
0x180010397  mov     rcx, [rsp+278h]; this
0x18001039f  mov     edx, 0A0Bh; void *
0x1800103a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800103aa  xor     eax, eax
0x1800103ac  jmp     loc_18001024C
0x1800103b1  mov     rcx, [rsp+278h]; this
0x1800103b9  lea     r8, aWil; "wil"
0x1800103c0  mov     edx, 0DCh; void *
0x1800103c5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800103ca  lea     rcx, [rsp+278h+var_248]
0x1800103cf  mov     ebx, eax
0x1800103d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800103d6  jmp     loc_180010240
0x1800103db  call    cs:__imp_GetLastError
0x1800103e1  cmp     eax, 2
0x1800103e4  jnz     short loc_1800103F7
0x1800103e6  lea     rcx, [rsp+278h+var_250]
0x1800103eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800103f0  xor     eax, eax
0x1800103f2  jmp     loc_180010254
0x1800103f7  mov     rcx, [rsp+278h]; this
0x1800103ff  lea     r8, aWil; "wil"
0x180010406  mov     edx, 0D0h; void *
0x18001040b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010410  jmp     loc_180010254
```
