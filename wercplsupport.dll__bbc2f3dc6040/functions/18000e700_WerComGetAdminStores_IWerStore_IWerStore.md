# WerComGetAdminStores(IWerStore * *,IWerStore * *)

- ea: `0x18000e700`
- end: `0x18000eaff`
- name: `?WerComGetAdminStores@@YAJPEAPEAUIWerStore@@0@Z`
- size: `1023`
- prototype: `__int64 __fastcall(struct IWerStore **, struct IWerStore **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002850`
- `0x180002a48`
- `0x180006c9c`
- `0x18000e520`
- `0x18000e648`
- `0x18000e700`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e7c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e7c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e7b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e7b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e8b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e937`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e8b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e82e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e82e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e972`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e972`

## pseudocode

```c
__int64 __fastcall WerComGetAdminStores(struct IWerStore **a1, struct IWerStore **a2)
{
  int v4; // ebx
  BOOL v5; // edi
  void **v6; // rbx
  HANDLE CurrentProcess; // rax
  int *v8; // r9
  signed int LastError; // eax
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  HRESULT v14; // eax
  int i; // r12d
  int v16; // eax
  HANDLE hObject; // [rsp+30h] [rbp-10h] BYREF
  LPVOID v19; // [rsp+38h] [rbp-8h] BYREF
  int v20; // [rsp+70h] [rbp+30h] BYREF
  int v21; // [rsp+80h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+48h] BYREF

  ppv = 0;
  v19 = 0;
  if ( a1 )
  {
    *a1 = 0;
    if ( !a2 )
      goto LABEL_6;
  }
  else if ( !a2 )
  {
    return 0;
  }
  *a2 = 0;
LABEL_6:
  if ( !(unsigned int)UtilIsUserAdmin(a1) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    v4 = -2147024891;
LABEL_66:
    if ( !a1 )
    {
LABEL_69:
      if ( a2 && *a2 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
        *a2 = 0;
      }
      goto LABEL_73;
    }
LABEL_67:
    if ( *a1 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = 0;
    }
    goto LABEL_69;
  }
  hObject = 0;
  v21 = 0;
  v5 = 0;
  v20 = 0;
  v6 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, v6) )
  {
    v10 = _werDetail::UtilLUAIsElevatedToken(hObject, &v21, &v20, v8);
    if ( (v10 & 0xC0000000) == 0xC0000000 )
    {
      v4 = v10 | 0x10000000;
    }
    else
    {
      if ( v20 )
        v5 = v21 == 0;
      v4 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( v4 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v12 = 104;
LABEL_28:
    v13 = (unsigned int)v4;
LABEL_65:
    WPP_SF_d(v11[2], v12, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, v13);
    goto LABEL_66;
  }
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    for ( i = 0; i < 10; ++i )
    {
      v4 = CoCreateInstance(&CLSID_ErcLuaSupport, 0, 0x17u, &IID_IErcLuaSupport, &v19);
      if ( v4 != -2146959352 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
      Sleep(0x64u);
    }
    if ( v4 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v12 = 109;
      goto LABEL_28;
    }
    v14 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v19 + 24LL))(v19, &ppv);
    v4 = v14;
    if ( v14 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v12 = 110;
      goto LABEL_64;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    v14 = CoCreateInstance(&CLSID_WerComSupport, 0, 1u, &IID_IWerStoreFactory, &ppv);
    v4 = v14;
    if ( v14 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v12 = 106;
LABEL_64:
      v13 = (unsigned int)v14;
      goto LABEL_65;
    }
  }
  if ( a1 )
  {
    v16 = (*(__int64 (__fastcall **)(LPVOID, struct IWerStore **))(*(_QWORD *)ppv + 24LL))(ppv, a1);
    v4 = v16;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
          (unsigned int)v16);
      goto LABEL_67;
    }
  }
  if ( a2 )
  {
    v14 = (*(__int64 (__fastcall **)(LPVOID, struct IWerStore **))(*(_QWORD *)ppv + 32LL))(ppv, a2);
    v4 = v14;
    if ( v14 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v12 = 112;
      goto LABEL_64;
    }
  }
  v4 = 0;
LABEL_73:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e700  mov     [rsp-28h+arg_8], rbx
0x18000e705  push    rbp
0x18000e706  push    rdi
0x18000e707  push    r12
0x18000e709  push    r14
0x18000e70b  push    r15
0x18000e70d  mov     rbp, rsp
0x18000e710  sub     rsp, 40h
0x18000e714  mov     [rbp+arg_18], 0
0x18000e71c  mov     r14, rdx
0x18000e71f  mov     [rbp+var_8], 0
0x18000e727  mov     r15, rcx
0x18000e72a  test    rcx, rcx
0x18000e72d  jnz     short loc_18000E73B
0x18000e72f  test    rdx, rdx
0x18000e732  jnz     short loc_18000E747
0x18000e734  xor     ebx, ebx
0x18000e736  jmp     loc_18000EAEB
0x18000e73b  mov     qword ptr [rcx], 0
0x18000e742  test    r14, r14
0x18000e745  jz      short loc_18000E74E
0x18000e747  mov     qword ptr [rdx], 0
0x18000e74e  call    ?UtilIsUserAdmin@@YAHPEAX@Z; UtilIsUserAdmin(void *)
0x18000e753  test    eax, eax
0x18000e755  jnz     short loc_18000E78D
0x18000e757  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e75e  lea     rdi, WPP_GLOBAL_Control
0x18000e765  cmp     rcx, rdi
0x18000e768  jz      short loc_18000E783
0x18000e76a  test    byte ptr [rcx+1Ch], 4
0x18000e76e  jz      short loc_18000E783
0x18000e770  mov     rcx, [rcx+10h]
0x18000e774  lea     edx, [rax+67h]
0x18000e777  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e77e  call    WPP_SF_
0x18000e783  mov     ebx, 80070005h
0x18000e788  jmp     loc_18000EA7D
0x18000e78d  lea     rcx, [rbp+hObject]
0x18000e791  mov     [rbp+hObject], 0
0x18000e799  mov     [rbp+arg_10], 0
0x18000e7a0  xor     edi, edi
0x18000e7a2  mov     [rbp+arg_0], 0
0x18000e7a9  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000e7ae  mov     rbx, rax
0x18000e7b1  call    cs:__imp_GetCurrentProcess
0x18000e7b7  mov     r8, rbx; TokenHandle
0x18000e7ba  lea     edx, [rdi+8]; DesiredAccess
0x18000e7bd  mov     rcx, rax; ProcessHandle
0x18000e7c0  call    cs:__imp_OpenProcessToken
0x18000e7c6  test    eax, eax
0x18000e7c8  jnz     short loc_18000E7EB
0x18000e7ca  call    cs:__imp_GetLastError
0x18000e7d0  mov     ebx, eax
0x18000e7d2  test    eax, eax
0x18000e7d4  jle     short loc_18000E7DF
0x18000e7d6  movzx   ebx, ax
0x18000e7d9  or      ebx, 80070000h
0x18000e7df  test    ebx, ebx
0x18000e7e1  mov     eax, 80004005h
0x18000e7e6  cmovns  ebx, eax
0x18000e7e9  jmp     short loc_18000E820
0x18000e7eb  mov     rcx, [rbp+hObject]; TokenHandle
0x18000e7ef  lea     r8, [rbp+arg_0]; int *
0x18000e7f3  lea     rdx, [rbp+arg_10]; void *
0x18000e7f7  call    ?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z; _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)
0x18000e7fc  mov     ecx, 0C0000000h
0x18000e801  mov     ebx, eax
0x18000e803  and     eax, ecx
0x18000e805  cmp     eax, ecx
0x18000e807  jnz     short loc_18000E80F
0x18000e809  bts     ebx, 1Ch
0x18000e80d  jmp     short loc_18000E820
0x18000e80f  cmp     [rbp+arg_0], edi
0x18000e812  jz      short loc_18000E81E
0x18000e814  cmp     [rbp+arg_10], edi
0x18000e817  jnz     short loc_18000E81E
0x18000e819  mov     edi, 1
0x18000e81e  xor     ebx, ebx
0x18000e820  mov     rcx, [rbp+hObject]; hObject
0x18000e824  lea     rax, [rcx+1]
0x18000e828  cmp     rax, 1
0x18000e82c  jbe     short loc_18000E834
0x18000e82e  call    cs:__imp_CloseHandle
0x18000e834  test    ebx, ebx
0x18000e836  jns     short loc_18000E866
0x18000e838  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e83f  lea     rdi, WPP_GLOBAL_Control
0x18000e846  cmp     rcx, rdi
0x18000e849  jz      loc_18000EA7D
0x18000e84f  test    byte ptr [rcx+1Ch], 1
0x18000e853  jz      loc_18000EA7D
0x18000e859  mov     edx, 68h ; 'h'
0x18000e85e  mov     r9d, ebx
0x18000e861  jmp     loc_18000EA6D
0x18000e866  test    edi, edi
0x18000e868  jnz     short loc_18000E8E9
0x18000e86a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e871  lea     rdi, WPP_GLOBAL_Control
0x18000e878  cmp     rcx, rdi
0x18000e87b  jz      short loc_18000E898
0x18000e87d  test    byte ptr [rcx+1Ch], 4
0x18000e881  jz      short loc_18000E898
0x18000e883  mov     rcx, [rcx+10h]
0x18000e887  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e88e  mov     edx, 69h ; 'i'
0x18000e893  call    WPP_SF_
0x18000e898  xor     edx, edx; pUnkOuter
0x18000e89a  lea     rax, [rbp+arg_18]
0x18000e89e  lea     r9, IID_IWerStoreFactory; riid
0x18000e8a5  mov     [rsp+40h+ppv], rax; ppv
0x18000e8aa  lea     rcx, CLSID_WerComSupport; rclsid
0x18000e8b1  lea     r8d, [rdx+1]; dwClsContext
0x18000e8b5  call    cs:__imp_CoCreateInstance
0x18000e8bb  mov     ebx, eax
0x18000e8bd  test    eax, eax
0x18000e8bf  jns     loc_18000E9E7
0x18000e8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8cc  cmp     rcx, rdi
0x18000e8cf  jz      loc_18000EA7D
0x18000e8d5  test    byte ptr [rcx+1Ch], 1
0x18000e8d9  jz      loc_18000EA7D
0x18000e8df  mov     edx, 6Ah ; 'j'
0x18000e8e4  jmp     loc_18000EA6A
0x18000e8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8f0  lea     rdi, WPP_GLOBAL_Control
0x18000e8f7  cmp     rcx, rdi
0x18000e8fa  jz      short loc_18000E917
0x18000e8fc  test    byte ptr [rcx+1Ch], 4
0x18000e900  jz      short loc_18000E917
0x18000e902  mov     rcx, [rcx+10h]
0x18000e906  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e90d  mov     edx, 6Bh ; 'k'
0x18000e912  call    WPP_SF_
0x18000e917  xor     r12d, r12d
0x18000e91a  xor     edx, edx; pUnkOuter
0x18000e91c  lea     rax, [rbp+var_8]
0x18000e920  lea     r9, IID_IErcLuaSupport; riid
0x18000e927  mov     [rsp+40h+ppv], rax; ppv
0x18000e92c  lea     rcx, CLSID_ErcLuaSupport; rclsid
0x18000e933  lea     r8d, [rdx+17h]; dwClsContext
0x18000e937  call    cs:__imp_CoCreateInstance
0x18000e93d  mov     ebx, eax
0x18000e93f  cmp     eax, 80080008h
0x18000e944  jnz     short loc_18000E981
0x18000e946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e94d  cmp     rcx, rdi
0x18000e950  jz      short loc_18000E96D
0x18000e952  test    byte ptr [rcx+1Ch], 4
0x18000e956  jz      short loc_18000E96D
0x18000e958  mov     rcx, [rcx+10h]
0x18000e95c  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000e963  mov     edx, 6Ch ; 'l'
0x18000e968  call    WPP_SF_
0x18000e96d  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000e972  call    cs:__imp_Sleep
0x18000e978  inc     r12d
0x18000e97b  cmp     r12d, 0Ah
0x18000e97f  jl      short loc_18000E91A
0x18000e981  test    ebx, ebx
0x18000e983  jns     short loc_18000E9A9
0x18000e985  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e98c  cmp     rcx, rdi
0x18000e98f  jz      loc_18000EA7D
0x18000e995  test    byte ptr [rcx+1Ch], 1
0x18000e999  jz      loc_18000EA7D
0x18000e99f  mov     edx, 6Dh ; 'm'
0x18000e9a4  jmp     loc_18000E85E
0x18000e9a9  mov     rcx, [rbp+var_8]
0x18000e9ad  lea     rdx, [rbp+arg_18]
0x18000e9b1  mov     rax, [rcx]
0x18000e9b4  mov     rax, [rax+18h]
0x18000e9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9bd  mov     ebx, eax
0x18000e9bf  test    eax, eax
0x18000e9c1  jns     short loc_18000E9E7
0x18000e9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9ca  cmp     rcx, rdi
0x18000e9cd  jz      loc_18000EA7D
0x18000e9d3  test    byte ptr [rcx+1Ch], 1
0x18000e9d7  jz      loc_18000EA7D
0x18000e9dd  mov     edx, 6Eh ; 'n'
0x18000e9e2  jmp     loc_18000EA6A
0x18000e9e7  test    r15, r15
0x18000e9ea  jz      short loc_18000EA31
0x18000e9ec  mov     rcx, [rbp+arg_18]
0x18000e9f0  mov     rdx, r15
0x18000e9f3  mov     rax, [rcx]
0x18000e9f6  mov     rax, [rax+18h]
0x18000e9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ff  mov     ebx, eax
0x18000ea01  test    eax, eax
0x18000ea03  jns     short loc_18000EA31
0x18000ea05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea0c  cmp     rcx, rdi
0x18000ea0f  jz      short loc_18000EA82
0x18000ea11  test    byte ptr [rcx+1Ch], 1
0x18000ea15  jz      short loc_18000EA82
0x18000ea17  mov     rcx, [rcx+10h]
0x18000ea1b  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000ea22  mov     edx, 6Fh ; 'o'
0x18000ea27  mov     r9d, eax
0x18000ea2a  call    WPP_SF_d
0x18000ea2f  jmp     short loc_18000EA82
0x18000ea31  test    r14, r14
0x18000ea34  jz      loc_18000EABF
0x18000ea3a  mov     rcx, [rbp+arg_18]
0x18000ea3e  mov     rdx, r14
0x18000ea41  mov     rax, [rcx]
0x18000ea44  mov     rax, [rax+20h]
0x18000ea48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea4d  mov     ebx, eax
0x18000ea4f  test    eax, eax
0x18000ea51  jns     short loc_18000EABF
0x18000ea53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea5a  cmp     rcx, rdi
0x18000ea5d  jz      short loc_18000EA7D
0x18000ea5f  test    byte ptr [rcx+1Ch], 1
0x18000ea63  jz      short loc_18000EA7D
0x18000ea65  mov     edx, 70h ; 'p'
0x18000ea6a  mov     r9d, eax
0x18000ea6d  mov     rcx, [rcx+10h]
0x18000ea71  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000ea78  call    WPP_SF_d
0x18000ea7d  test    r15, r15
0x18000ea80  jz      short loc_18000EA9D
0x18000ea82  mov     rcx, [r15]
0x18000ea85  test    rcx, rcx
0x18000ea88  jz      short loc_18000EA9D
0x18000ea8a  mov     rax, [rcx]
0x18000ea8d  mov     rax, [rax+10h]
0x18000ea91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea96  mov     qword ptr [r15], 0
0x18000ea9d  test    r14, r14
0x18000eaa0  jz      short loc_18000EAC1
0x18000eaa2  mov     rcx, [r14]
0x18000eaa5  test    rcx, rcx
0x18000eaa8  jz      short loc_18000EAC1
0x18000eaaa  mov     rax, [rcx]
0x18000eaad  mov     rax, [rax+10h]
0x18000eab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab6  mov     qword ptr [r14], 0
0x18000eabd  jmp     short loc_18000EAC1
0x18000eabf  xor     ebx, ebx
0x18000eac1  mov     rcx, [rbp+arg_18]
0x18000eac5  test    rcx, rcx
0x18000eac8  jz      short loc_18000EAD6
0x18000eaca  mov     rax, [rcx]
0x18000eacd  mov     rax, [rax+10h]
0x18000ead1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead6  mov     rcx, [rbp+var_8]
0x18000eada  test    rcx, rcx
0x18000eadd  jz      short loc_18000EAEB
0x18000eadf  mov     rax, [rcx]
0x18000eae2  mov     rax, [rax+10h]
0x18000eae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaeb  mov     eax, ebx
0x18000eaed  mov     rbx, [rsp+40h+arg_8]
0x18000eaf2  add     rsp, 40h
0x18000eaf6  pop     r15
0x18000eaf8  pop     r14
0x18000eafa  pop     r12
0x18000eafc  pop     rdi
0x18000eafd  pop     rbp
0x18000eafe  retn
```
