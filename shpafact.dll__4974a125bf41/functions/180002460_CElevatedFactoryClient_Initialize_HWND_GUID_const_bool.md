# CElevatedFactoryClient::_Initialize(HWND__ *,_GUID const &,bool)

- ea: `0x180002460`
- end: `0x1800026a4`
- name: `?_Initialize@CElevatedFactoryClient@@IEAAJPEAUHWND__@@AEBU_GUID@@_N@Z`
- size: `580`
- prototype: `__int64 __fastcall(CElevatedFactoryClient *__hidden this, HWND, const struct _GUID *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f60`
- `0x180001f70`

## callees

- `0x180002340`
- `0x180002460`
- `0x1800026ac`
- `0x1800026d4`
- `0x1800036c0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002589`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002589`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800024c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800024c2`
- `ole32!CoGetObject` at `0x1800025f9`
- `ole32!CoGetObject` at `0x1800025f9`
- `USER32!LoadCursorW` at `0x180002542`
- `USER32!LoadCursorW` at `0x180002542`
- `USER32!SetCursor` at `0x180002553`
- `USER32!SetCursor` at `0x180002626`
- `USER32!SetCursor` at `0x180002553`
- `USER32!SetCursor` at `0x180002626`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryClient::_Initialize(LPVOID *this, HWND a2, const struct _GUID *a3, char a4)
{
  const GUID *v4; // r14
  _QWORD *v6; // r15
  HRESULT Instance; // ebx
  __int64 v9; // rcx
  HCURSOR v10; // rsi
  HCURSOR CursorW; // rax
  HCURSOR v12; // rdi
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  void *v15; // [rsp+38h] [rbp-C8h] BYREF
  BIND_OPTS pBindOptions[3]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[56]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszName[304]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = (const GUID *)(this + 1);
  v6 = this + 3;
  *(struct _GUID *)(this + 1) = *a3;
  Instance = CoCreateInstance(
               &CLSID_ElevatedFactoryServerManager,
               0,
               1u,
               &GUID_36df1a3d_973d_4956_b55a_47de453e8103,
               this + 3);
  if ( Instance < 0 )
    goto LABEL_22;
  v9 = *v6;
  v14 = 0;
  Instance = (*(__int64 (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v9 + 24LL))(v9, v4, &v14);
  if ( Instance < 0 )
    goto LABEL_22;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids);
    v10 = 0;
    if ( a4 )
    {
      CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
      v12 = CursorW;
      if ( CursorW )
        v10 = SetCursor(CursorW);
    }
    else
    {
      v12 = 0;
    }
    v15 = 0;
    memset(pBindOptions, 0, sizeof(pBindOptions));
    if ( StringFromGUID2(v4, sz, 50) )
    {
      Instance = StringCchPrintfW(pszName, 0x12Cu, L"Elevation:Administrator!new:%s", sz);
      if ( Instance >= 0 )
      {
        pBindOptions[0].cbStruct = 48;
        *(_QWORD *)&pBindOptions[2].grfMode = a2;
        pBindOptions[1].grfFlags = 4;
        *(_OWORD *)&pBindOptions[0].grfFlags = 0;
        *(_OWORD *)&pBindOptions[1].grfMode = 0;
        Instance = CoGetObject(pszName, pBindOptions, &GUID_804bd226_af47_4d71_b492_443a57610b08, &v15);
        if ( Instance >= 0 )
          Instance = (*(__int64 (__fastcall **)(_QWORD, const GUID *, void *))(*(_QWORD *)*v6 + 32LL))(*v6, v4, v15);
      }
    }
    else
    {
      Instance = -2147024882;
    }
    if ( v12 )
      SetCursor(v10);
    if ( v15 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( Instance < 0 )
    {
LABEL_22:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids,
          (unsigned int)Instance);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180002460  mov     [rsp-8+arg_10], rbx
0x180002465  mov     [rsp-8+arg_18], rsi
0x18000246a  push    rbp
0x18000246b  push    rdi
0x18000246c  push    r12
0x18000246e  push    r14
0x180002470  push    r15
0x180002472  lea     rbp, [rsp-250h]
0x18000247a  sub     rsp, 350h
0x180002481  mov     rax, cs:__security_cookie
0x180002488  xor     rax, rsp
0x18000248b  mov     [rbp+270h+var_30], rax
0x180002492  movups  xmm0, xmmword ptr [r8]
0x180002496  lea     r14, [rcx+8]
0x18000249a  mov     r12, rdx
0x18000249d  lea     r15, [rcx+18h]
0x1800024a1  xor     edx, edx; pUnkOuter
0x1800024a3  mov     dil, r9b
0x1800024a6  mov     [rsp+370h+ppv], r15; ppv
0x1800024ab  lea     r9, _GUID_36df1a3d_973d_4956_b55a_47de453e8103; riid
0x1800024b2  lea     rcx, CLSID_ElevatedFactoryServerManager; rclsid
0x1800024b9  lea     r8d, [rdx+1]; dwClsContext
0x1800024bd  movdqu  xmmword ptr [r14], xmm0
0x1800024c2  call    cs:__imp_CoCreateInstance
0x1800024c8  lea     rsi, WPP_GLOBAL_Control
0x1800024cf  mov     ebx, eax
0x1800024d1  test    eax, eax
0x1800024d3  js      loc_18000264D
0x1800024d9  mov     rcx, [r15]
0x1800024dc  lea     r8, [rsp+370h+var_340]
0x1800024e1  mov     [rsp+370h+var_340], 0
0x1800024e9  mov     rdx, r14
0x1800024ec  mov     rax, [rcx]
0x1800024ef  mov     rax, [rax+18h]
0x1800024f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f8  mov     ebx, eax
0x1800024fa  test    eax, eax
0x1800024fc  js      loc_18000264D
0x180002502  cmp     [rsp+370h+var_340], 0
0x180002507  jnz     loc_180002677
0x18000250d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002514  cmp     rcx, rsi
0x180002517  jz      short loc_180002534
0x180002519  test    byte ptr [rcx+1Ch], 8
0x18000251d  jz      short loc_180002534
0x18000251f  mov     rcx, [rcx+10h]
0x180002523  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x18000252a  mov     edx, 0Bh
0x18000252f  call    WPP_SF_
0x180002534  xor     esi, esi
0x180002536  test    dil, dil
0x180002539  jz      short loc_18000255E
0x18000253b  mov     edx, 7F02h; lpCursorName
0x180002540  xor     ecx, ecx; hInstance
0x180002542  call    cs:__imp_LoadCursorW
0x180002548  mov     rdi, rax
0x18000254b  test    rax, rax
0x18000254e  jz      short loc_180002560
0x180002550  mov     rcx, rax; hCursor
0x180002553  call    cs:__imp_SetCursor
0x180002559  mov     rsi, rax
0x18000255c  jmp     short loc_180002560
0x18000255e  xor     edi, edi
0x180002560  xorps   xmm0, xmm0
0x180002563  mov     [rsp+370h+var_338], 0
0x18000256c  mov     r8d, 32h ; '2'; cchMax
0x180002572  lea     rdx, [rsp+370h+sz]; lpsz
0x180002577  mov     rcx, r14; rguid
0x18000257a  movups  xmmword ptr [rsp+370h+pBindOptions.cbStruct], xmm0
0x18000257f  movups  [rsp+370h+var_320], xmm0
0x180002584  movups  [rsp+370h+var_310], xmm0
0x180002589  call    cs:__imp_StringFromGUID2
0x18000258f  test    eax, eax
0x180002591  jnz     short loc_18000259D
0x180002593  mov     ebx, 8007000Eh
0x180002598  jmp     loc_18000261E
0x18000259d  lea     r9, [rsp+370h+sz]
0x1800025a2  mov     edx, 12Ch; unsigned __int64
0x1800025a7  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x1800025ae  lea     rcx, [rbp+270h+pszName]; unsigned __int16 *
0x1800025b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025b7  mov     ebx, eax
0x1800025b9  test    eax, eax
0x1800025bb  js      short loc_18000261E
0x1800025bd  xorps   xmm0, xmm0
0x1800025c0  mov     [rsp+370h+pBindOptions.cbStruct], 30h ; '0'
0x1800025c8  xorps   xmm1, xmm1
0x1800025cb  mov     qword ptr [rsp+370h+var_310+8], r12
0x1800025d0  lea     r9, [rsp+370h+var_338]; ppv
0x1800025d5  mov     dword ptr [rsp+370h+var_320+4], 4
0x1800025dd  lea     r8, _GUID_804bd226_af47_4d71_b492_443a57610b08; riid
0x1800025e4  lea     rdx, [rsp+370h+pBindOptions]; pBindOptions
0x1800025e9  lea     rcx, [rbp+270h+pszName]; pszName
0x1800025ed  movdqu  xmmword ptr [rsp+370h+pBindOptions.grfFlags], xmm0
0x1800025f3  movdqu  [rsp+370h+var_320+8], xmm1
0x1800025f9  call    cs:__imp_CoGetObject
0x1800025ff  mov     ebx, eax
0x180002601  test    eax, eax
0x180002603  js      short loc_18000261E
0x180002605  mov     rcx, [r15]
0x180002608  mov     rdx, r14
0x18000260b  mov     r8, [rsp+370h+var_338]
0x180002610  mov     rax, [rcx]
0x180002613  mov     rax, [rax+20h]
0x180002617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261c  mov     ebx, eax
0x18000261e  test    rdi, rdi
0x180002621  jz      short loc_18000262C
0x180002623  mov     rcx, rsi; hCursor
0x180002626  call    cs:__imp_SetCursor
0x18000262c  mov     rcx, [rsp+370h+var_338]
0x180002631  test    rcx, rcx
0x180002634  jz      short loc_180002642
0x180002636  mov     rax, [rcx]
0x180002639  mov     rax, [rax+10h]
0x18000263d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002642  test    ebx, ebx
0x180002644  jns     short loc_180002677
0x180002646  lea     rsi, WPP_GLOBAL_Control
0x18000264d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002654  cmp     rcx, rsi
0x180002657  jz      short loc_180002677
0x180002659  test    byte ptr [rcx+1Ch], 4
0x18000265d  jz      short loc_180002677
0x18000265f  mov     rcx, [rcx+10h]
0x180002663  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x18000266a  mov     edx, 0Ch
0x18000266f  mov     r9d, ebx
0x180002672  call    WPP_SF_d
0x180002677  mov     eax, ebx
0x180002679  mov     rcx, [rbp+270h+var_30]
0x180002680  xor     rcx, rsp; StackCookie
0x180002683  call    __security_check_cookie
0x180002688  lea     r11, [rsp+370h+var_20]
0x180002690  mov     rbx, [r11+40h]
0x180002694  mov     rsi, [r11+48h]
0x180002698  mov     rsp, r11
0x18000269b  pop     r15
0x18000269d  pop     r14
0x18000269f  pop     r12
0x1800026a1  pop     rdi
0x1800026a2  pop     rbp
0x1800026a3  retn
```
