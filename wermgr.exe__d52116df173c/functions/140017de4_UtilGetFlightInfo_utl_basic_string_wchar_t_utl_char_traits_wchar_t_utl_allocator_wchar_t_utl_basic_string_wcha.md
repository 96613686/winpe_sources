# UtilGetFlightInfo(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140017de4`
- end: `0x140018173`
- name: `?UtilGetFlightInfo@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0@Z`
- size: `911`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004e18`
- `0x14000705c`

## callees

- `0x14000db44`
- `0x14000e340`
- `0x140017de4`
- `0x14001a504`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140017e00`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140017e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017fc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017ff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017fc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140017ff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018151`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140017eb5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140017eb5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001815c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001815c`

## pseudocode

```c
__int64 __fastcall UtilGetFlightInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  HRESULT v6; // ebx
  __int64 v7; // r8
  HRESULT v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rcx
  LPVOID v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, LPVOID *); // rsi
  void *v16; // rcx
  void *v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, LPVOID *); // rsi
  void *v20; // rcx
  void *v21; // rcx
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // r8
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-18h]
  __int64 v27; // [rsp+98h] [rbp+48h] BYREF
  LPVOID v28; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+58h] BYREF

  v6 = CoInitializeEx(0, 0);
  pv = 0;
  v28 = 0;
  v27 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v7);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v7);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147417850 )
  {
    v8 = v6;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 125;
      v11 = (unsigned int)v6;
LABEL_62:
      WPP_SF_d(v9[2], v10, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v11);
      goto LABEL_63;
    }
    goto LABEL_63;
  }
  ppv = 0;
  p_pv = (LPVOID *)&v27;
  v12 = v27;
  v27 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v8 = CoCreateInstance(
         &GUID_3185a766_b338_11e4_a71e_12e3f512a338,
         0,
         1u,
         &GUID_e833feb2_c58a_45e4_8d93_08874744febb,
         &ppv);
  if ( ppv )
  {
    v13 = *p_pv;
    *p_pv = ppv;
    if ( v13 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_63;
    v10 = 126;
    goto LABEL_19;
  }
  v14 = v27;
  v15 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v27 + 48LL);
  ppv = 0;
  p_pv = &pv;
  v16 = pv;
  pv = 0;
  if ( v16 )
    CoTaskMemFree(v16);
  v8 = v15(v14, &ppv);
  if ( ppv )
  {
    v17 = *p_pv;
    *p_pv = ppv;
    if ( v17 )
      CoTaskMemFree(v17);
  }
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_63;
    v10 = 127;
    goto LABEL_19;
  }
  v18 = v27;
  v19 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v27 + 80LL);
  ppv = 0;
  p_pv = &v28;
  v20 = v28;
  v28 = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  v8 = v19(v18, &ppv);
  if ( ppv )
  {
    v21 = *p_pv;
    *p_pv = ppv;
    if ( v21 )
      CoTaskMemFree(v21);
  }
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_63;
    v10 = 128;
LABEL_19:
    v11 = (unsigned int)v8;
    goto LABEL_62;
  }
  if ( pv && v28 )
  {
    v22 = -1;
    if ( pv )
    {
      v23 = -1;
      do
        ++v23;
      while ( *((_WORD *)pv + v23) );
    }
    else
    {
      v23 = 0;
    }
    if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, pv, v23) )
    {
      if ( v28 )
      {
        do
          ++v22;
        while ( *((_WORD *)v28 + v22) );
      }
      else
      {
        v22 = 0;
      }
      if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v28, v22) )
      {
        v8 = 0;
        goto LABEL_63;
      }
      v8 = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_63;
      v10 = 131;
    }
    else
    {
      v8 = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_63;
      v10 = 130;
    }
    v11 = 2147942414LL;
    goto LABEL_62;
  }
  v8 = -2147467261;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 129;
    v11 = 2147500035LL;
    goto LABEL_62;
  }
LABEL_63:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    CoTaskMemFree(v28);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v6 >= 0 )
    CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140017de4  push    rbp
0x140017de6  push    rbx
0x140017de7  push    rsi
0x140017de8  push    rdi
0x140017de9  push    r12
0x140017deb  push    r14
0x140017ded  push    r15
0x140017def  mov     rbp, rsp
0x140017df2  sub     rsp, 50h
0x140017df6  mov     r15, rdx
0x140017df9  mov     r14, rcx
0x140017dfc  xor     edx, edx; dwCoInit
0x140017dfe  xor     ecx, ecx; pvReserved
0x140017e00  call    cs:__imp_CoInitializeEx
0x140017e06  mov     ebx, eax
0x140017e08  mov     [rbp+arg_0], eax
0x140017e0b  xor     r12d, r12d
0x140017e0e  mov     [rbp+pv], r12
0x140017e12  mov     [rbp+arg_10], r12
0x140017e16  mov     [rbp+arg_8], r12
0x140017e1a  test    r14, r14
0x140017e1d  jnz     short loc_140017E24
0x140017e1f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140017e24  test    r15, r15
0x140017e27  jnz     short loc_140017E2E
0x140017e29  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140017e2e  mov     ecx, 80000000h
0x140017e33  lea     eax, [rbx+rcx]
0x140017e36  test    ecx, eax
0x140017e38  jnz     short loc_140017E72
0x140017e3a  cmp     ebx, 80010106h
0x140017e40  jz      short loc_140017E72
0x140017e42  mov     edi, ebx
0x140017e44  lea     rax, WPP_GLOBAL_Control
0x140017e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e52  cmp     rcx, rax
0x140017e55  jz      loc_140018122
0x140017e5b  test    byte ptr [rcx+1Ch], 1
0x140017e5f  jz      loc_140018122
0x140017e65  mov     edx, 7Dh ; '}'
0x140017e6a  mov     r9d, ebx
0x140017e6d  jmp     loc_140018111
0x140017e72  mov     [rbp+var_20], r12
0x140017e76  lea     rax, [rbp+arg_8]
0x140017e7a  mov     [rbp+var_18], rax
0x140017e7e  mov     rcx, [rbp+arg_8]
0x140017e82  mov     [rbp+arg_8], r12
0x140017e86  test    rcx, rcx
0x140017e89  jz      short loc_140017E98
0x140017e8b  mov     rax, [rcx]
0x140017e8e  mov     rax, [rax+10h]
0x140017e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017e97  nop
0x140017e98  lea     rax, [rbp+var_20]
0x140017e9c  mov     [rsp+50h+ppv], rax; ppv
0x140017ea1  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x140017ea8  xor     edx, edx; pUnkOuter
0x140017eaa  lea     r8d, [rdx+1]; dwClsContext
0x140017eae  lea     rcx, _GUID_3185a766_b338_11e4_a71e_12e3f512a338; rclsid
0x140017eb5  call    cs:__imp_CoCreateInstance
0x140017ebb  mov     edi, eax
0x140017ebd  mov     rdx, [rbp+var_20]
0x140017ec1  test    rdx, rdx
0x140017ec4  jz      short loc_140017EE2
0x140017ec6  mov     rax, [rbp+var_18]
0x140017eca  mov     rcx, [rax]
0x140017ecd  mov     [rax], rdx
0x140017ed0  test    rcx, rcx
0x140017ed3  jz      short loc_140017EE2
0x140017ed5  mov     rax, [rcx]
0x140017ed8  mov     rax, [rax+10h]
0x140017edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017ee1  nop
0x140017ee2  test    edi, edi
0x140017ee4  jns     short loc_140017F14
0x140017ee6  lea     rax, WPP_GLOBAL_Control
0x140017eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ef4  cmp     rcx, rax
0x140017ef7  jz      loc_140018122
0x140017efd  test    byte ptr [rcx+1Ch], 1
0x140017f01  jz      loc_140018122
0x140017f07  mov     edx, 7Eh ; '~'
0x140017f0c  mov     r9d, edi
0x140017f0f  jmp     loc_140018111
0x140017f14  mov     rdi, [rbp+arg_8]
0x140017f18  mov     rax, [rdi]
0x140017f1b  mov     rsi, [rax+30h]
0x140017f1f  mov     [rbp+var_20], r12
0x140017f23  lea     rax, [rbp+pv]
0x140017f27  mov     [rbp+var_18], rax
0x140017f2b  mov     rcx, [rbp+pv]; pv
0x140017f2f  mov     [rbp+pv], r12
0x140017f33  test    rcx, rcx
0x140017f36  jz      short loc_140017F3F
0x140017f38  call    cs:__imp_CoTaskMemFree
0x140017f3e  nop
0x140017f3f  lea     rdx, [rbp+var_20]
0x140017f43  mov     rcx, rdi
0x140017f46  mov     rax, rsi
0x140017f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017f4e  mov     edi, eax
0x140017f50  mov     rax, [rbp+var_20]
0x140017f54  test    rax, rax
0x140017f57  jz      short loc_140017F6E
0x140017f59  mov     rdx, [rbp+var_18]
0x140017f5d  mov     rcx, [rdx]; pv
0x140017f60  mov     [rdx], rax
0x140017f63  test    rcx, rcx
0x140017f66  jz      short loc_140017F6E
0x140017f68  call    cs:__imp_CoTaskMemFree
0x140017f6e  test    edi, edi
0x140017f70  jns     short loc_140017F9D
0x140017f72  lea     rax, WPP_GLOBAL_Control
0x140017f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f80  cmp     rcx, rax
0x140017f83  jz      loc_140018122
0x140017f89  test    byte ptr [rcx+1Ch], 1
0x140017f8d  jz      loc_140018122
0x140017f93  mov     edx, 7Fh
0x140017f98  jmp     loc_140017F0C
0x140017f9d  mov     rdi, [rbp+arg_8]
0x140017fa1  mov     rax, [rdi]
0x140017fa4  mov     rsi, [rax+50h]
0x140017fa8  mov     [rbp+var_20], r12
0x140017fac  lea     rax, [rbp+arg_10]
0x140017fb0  mov     [rbp+var_18], rax
0x140017fb4  mov     rcx, [rbp+arg_10]; pv
0x140017fb8  mov     [rbp+arg_10], r12
0x140017fbc  test    rcx, rcx
0x140017fbf  jz      short loc_140017FC8
0x140017fc1  call    cs:__imp_CoTaskMemFree
0x140017fc7  nop
0x140017fc8  lea     rdx, [rbp+var_20]
0x140017fcc  mov     rcx, rdi
0x140017fcf  mov     rax, rsi
0x140017fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017fd7  mov     edi, eax
0x140017fd9  mov     rdx, [rbp+var_20]
0x140017fdd  test    rdx, rdx
0x140017fe0  jz      short loc_140017FF7
0x140017fe2  mov     rax, [rbp+var_18]
0x140017fe6  mov     rcx, [rax]; pv
0x140017fe9  mov     [rax], rdx
0x140017fec  test    rcx, rcx
0x140017fef  jz      short loc_140017FF7
0x140017ff1  call    cs:__imp_CoTaskMemFree
0x140017ff7  test    edi, edi
0x140017ff9  jns     short loc_140018026
0x140017ffb  lea     rax, WPP_GLOBAL_Control
0x140018002  mov     rcx, cs:WPP_GLOBAL_Control
0x140018009  cmp     rcx, rax
0x14001800c  jz      loc_140018122
0x140018012  test    byte ptr [rcx+1Ch], 1
0x140018016  jz      loc_140018122
0x14001801c  mov     edx, 80h
0x140018021  jmp     loc_140017F0C
0x140018026  mov     rdx, [rbp+pv]
0x14001802a  test    rdx, rdx
0x14001802d  jz      loc_1400180E8
0x140018033  cmp     [rbp+arg_10], r12
0x140018037  jz      loc_1400180E8
0x14001803d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140018041  test    rdx, rdx
0x140018044  jz      short loc_140018055
0x140018046  mov     r8, rdi
0x140018049  inc     r8
0x14001804c  cmp     [rdx+r8*2], r12w
0x140018051  jnz     short loc_140018049
0x140018053  jmp     short loc_140018058
0x140018055  mov     r8, r12
0x140018058  mov     rcx, r14
0x14001805b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140018060  test    al, al
0x140018062  jnz     short loc_140018097
0x140018064  mov     edi, 8007000Eh
0x140018069  lea     rax, WPP_GLOBAL_Control
0x140018070  mov     rcx, cs:WPP_GLOBAL_Control
0x140018077  cmp     rcx, rax
0x14001807a  jz      loc_140018122
0x140018080  test    byte ptr [rcx+1Ch], 1
0x140018084  jz      loc_140018122
0x14001808a  mov     edx, 82h
0x14001808f  mov     r9d, 8007000Eh
0x140018095  jmp     short loc_140018111
0x140018097  mov     rdx, [rbp+arg_10]
0x14001809b  test    rdx, rdx
0x14001809e  jz      short loc_1400180AC
0x1400180a0  inc     rdi
0x1400180a3  cmp     [rdx+rdi*2], r12w
0x1400180a8  jnz     short loc_1400180A0
0x1400180aa  jmp     short loc_1400180AF
0x1400180ac  mov     rdi, r12
0x1400180af  mov     r8, rdi
0x1400180b2  mov     rcx, r15
0x1400180b5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400180ba  test    al, al
0x1400180bc  jnz     short loc_1400180E3
0x1400180be  mov     edi, 8007000Eh
0x1400180c3  lea     rax, WPP_GLOBAL_Control
0x1400180ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180d1  cmp     rcx, rax
0x1400180d4  jz      short loc_140018122
0x1400180d6  test    byte ptr [rcx+1Ch], 1
0x1400180da  jz      short loc_140018122
0x1400180dc  mov     edx, 83h
0x1400180e1  jmp     short loc_14001808F
0x1400180e3  mov     edi, r12d
0x1400180e6  jmp     short loc_140018122
0x1400180e8  mov     edi, 80004003h
0x1400180ed  lea     rax, WPP_GLOBAL_Control
0x1400180f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180fb  cmp     rcx, rax
0x1400180fe  jz      short loc_140018122
0x140018100  test    byte ptr [rcx+1Ch], 1
0x140018104  jz      short loc_140018122
0x140018106  mov     edx, 81h
0x14001810b  mov     r9d, 80004003h
0x140018111  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140018118  mov     rcx, [rcx+10h]
0x14001811c  call    WPP_SF_d
0x140018121  nop
0x140018122  mov     rcx, [rbp+arg_8]
0x140018126  test    rcx, rcx
0x140018129  jz      short loc_140018138
0x14001812b  mov     rax, [rcx]
0x14001812e  mov     rax, [rax+10h]
0x140018132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018137  nop
0x140018138  mov     rcx, [rbp+arg_10]; pv
0x14001813c  test    rcx, rcx
0x14001813f  jz      short loc_140018148
0x140018141  call    cs:__imp_CoTaskMemFree
0x140018147  nop
0x140018148  mov     rcx, [rbp+pv]; pv
0x14001814c  test    rcx, rcx
0x14001814f  jz      short loc_140018158
0x140018151  call    cs:__imp_CoTaskMemFree
0x140018157  nop
0x140018158  test    ebx, ebx
0x14001815a  js      short loc_140018162
0x14001815c  call    cs:__imp_CoUninitialize
0x140018162  mov     eax, edi
0x140018164  add     rsp, 50h
0x140018168  pop     r15
0x14001816a  pop     r14
0x14001816c  pop     r12
0x14001816e  pop     rdi
0x14001816f  pop     rsi
0x140018170  pop     rbx
0x140018171  pop     rbp
0x140018172  retn
```
