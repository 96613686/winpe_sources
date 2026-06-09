# RegisterFactories

- ea: `0x140005d74`
- end: `0x140005ffd`
- name: `RegisterFactories`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140006c88`

## callees

- `0x140001008`
- `0x140005d74`
- `0x14000a358`
- `0x14000a568`
- `0x140015a7c`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005eb7`
- `KERNEL32!GetCurrentThreadId` at `0x140005eb7`
- `USER32!DispatchMessageA` at `0x140005f9d`
- `USER32!DispatchMessageA` at `0x140005f9d`
- `USER32!GetMessageA` at `0x140005faf`
- `USER32!GetMessageA` at `0x140005faf`
- `ole32!CoRevokeClassObject` at `0x140005fc0`
- `ole32!CoRevokeClassObject` at `0x140005fc0`
- `ole32!CoRegisterClassObject` at `0x140005eda`
- `ole32!CoRegisterClassObject` at `0x140005eda`
- `ADVAPI32!RegCloseKey` at `0x140005e57`
- `ADVAPI32!RegCloseKey` at `0x140005e66`
- `ADVAPI32!RegCloseKey` at `0x140005e57`
- `ADVAPI32!RegCloseKey` at `0x140005e66`

## pseudocode

```c
__int64 __fastcall RegisterFactories(struct IUnknownVtbl *a1)
{
  HRESULT v2; // edi
  int v3; // ebx
  IUnknown *v4; // rbx
  __int64 v5; // rax
  __int64 *wParam; // rsi
  unsigned int lParam; // r14d
  __int64 v8; // rdi
  __int64 v9; // rcx
  int MessageA; // eax
  int lpdwRegister; // [rsp+20h] [rbp-49h]
  __int128 v13; // [rsp+50h] [rbp-19h] BYREF
  __int64 v14; // [rsp+60h] [rbp-9h]
  MSG Msg; // [rsp+68h] [rbp-1h] BYREF
  DWORD dwRegister; // [rsp+D8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+E0h] [rbp+77h] BYREF
  HKEY phkResult; // [rsp+E8h] [rbp+7Fh] BYREF

  memset(&Msg, 0, sizeof(Msg));
  dwRegister = 0;
  hKey = 0;
  phkResult = 0;
  if ( Global::g_fWindowsNT )
  {
    OpenRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &phkResult);
    OpenRegSettings(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
    if ( CheckWSHFlag(L"Enabled", phkResult, hKey, 1) )
    {
      v3 = 0;
      if ( !CheckWSHFlag(L"Remote", phkResult, hKey, 0) )
        v3 = -2147467237;
      v2 = v3;
    }
    else
    {
      v2 = -2147467237;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    v2 = -2147467237;
  }
  LogSecurityMessage(v2 < 0, ((v2 >> 31) & 0x9B) + 3055);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v4 = (IUnknown *)operator new(0x18u);
  if ( !v4 )
    return (unsigned int)-2147024882;
  v4[2].lpVtbl = a1;
  v4->lpVtbl = (struct IUnknownVtbl *)&CWSHRemoteFactory::`vftable';
  LODWORD(v4[1].lpVtbl) = 1;
  HIDWORD(v4[1].lpVtbl) = GetCurrentThreadId();
  v2 = CoRegisterClassObject(&CLSID_WSHRemote, v4, 0x14u, 0, &dwRegister);
  if ( v2 < 0 )
    goto LABEL_30;
  while ( 1 )
  {
    MessageA = GetMessageA(&Msg, 0, 0, 0);
    if ( !MessageA || MessageA == -1 )
      break;
    if ( Msg.message == 1034 )
    {
      wParam = (__int64 *)Msg.wParam;
      lParam = Msg.lParam;
      v8 = 0;
      v13 = 0;
      v14 = 0;
      do
      {
        v9 = wParam[v8 + 21];
        if ( v9 )
        {
          LOWORD(lpdwRegister) = 1;
          (*(void (__fastcall **)(__int64, _QWORD, GUID *, __int64, int, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 48LL))(
            v9,
            lParam,
            &GUID_NULL,
            1024,
            lpdwRegister,
            &v13,
            0,
            0,
            0);
        }
        ++v8;
      }
      while ( v8 != 50 );
      v5 = *wParam;
    }
    else
    {
      if ( Msg.message != 1035 )
        goto LABEL_26;
      v5 = *(_QWORD *)Msg.wParam;
    }
    (*(void (**)(void))(v5 + 16))();
LABEL_26:
    DispatchMessageA(&Msg);
  }
  v2 = CoRevokeClassObject(dwRegister);
  if ( v2 >= 0 )
    v2 = 0;
LABEL_30:
  ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140005d74  mov     [rsp-8+arg_0], rbx
0x140005d79  push    rbp
0x140005d7a  push    rsi
0x140005d7b  push    rdi
0x140005d7c  push    r12
0x140005d7e  push    r14
0x140005d80  lea     rbp, [rsp-37h]
0x140005d85  sub     rsp, 0A0h
0x140005d8c  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140005d93  xorps   xmm0, xmm0
0x140005d96  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x140005d9a  mov     rsi, rcx
0x140005d9d  mov     [rbp+57h+dwRegister], 0
0x140005da4  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x140005da8  mov     [rbp+57h+hKey], 0
0x140005db0  mov     r12d, 1
0x140005db6  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x140005dba  mov     [rbp+57h+phkResult], 0
0x140005dc2  jnz     short loc_140005DCE
0x140005dc4  mov     edi, 8000401Bh
0x140005dc9  jmp     loc_140005E6C
0x140005dce  mov     ebx, 20019h
0x140005dd3  lea     r9, [rbp+57h+phkResult]; phkResult
0x140005dd7  mov     r8d, ebx; samDesired
0x140005dda  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x140005de1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140005de8  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140005ded  lea     r9, [rbp+57h+hKey]; phkResult
0x140005df1  mov     r8d, ebx; samDesired
0x140005df4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x140005dfb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005e02  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x140005e07  mov     r8, [rbp+57h+hKey]; HKEY
0x140005e0b  lea     rcx, aEnabled; "Enabled"
0x140005e12  mov     rdx, [rbp+57h+phkResult]; hKey
0x140005e16  mov     r9b, r12b; bool
0x140005e19  call    ?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z; CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)
0x140005e1e  test    al, al
0x140005e20  jnz     short loc_140005E29
0x140005e22  mov     edi, 8000401Bh
0x140005e27  jmp     short loc_140005E4E
0x140005e29  mov     r8, [rbp+57h+hKey]; HKEY
0x140005e2d  lea     rcx, aRemote; "Remote"
0x140005e34  mov     rdx, [rbp+57h+phkResult]; hKey
0x140005e38  xor     r9d, r9d; bool
0x140005e3b  xor     ebx, ebx
0x140005e3d  call    ?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z; CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)
0x140005e42  mov     edi, 8000401Bh
0x140005e47  test    al, al
0x140005e49  cmovz   ebx, edi
0x140005e4c  mov     edi, ebx
0x140005e4e  mov     rcx, [rbp+57h+hKey]; hKey
0x140005e52  test    rcx, rcx
0x140005e55  jz      short loc_140005E5D
0x140005e57  call    cs:__imp_RegCloseKey
0x140005e5d  mov     rcx, [rbp+57h+phkResult]; hKey
0x140005e61  test    rcx, rcx
0x140005e64  jz      short loc_140005E6C
0x140005e66  call    cs:__imp_RegCloseKey
0x140005e6c  mov     edx, edi
0x140005e6e  mov     ecx, edi
0x140005e70  sar     edx, 1Fh
0x140005e73  and     edx, 9Bh
0x140005e79  shr     ecx, 1Fh; bool
0x140005e7c  add     edx, 0BEFh; unsigned int
0x140005e82  call    ?LogSecurityMessage@@YAX_NI@Z; LogSecurityMessage(bool,uint)
0x140005e87  test    edi, edi
0x140005e89  js      loc_140005FE4
0x140005e8f  mov     ecx, 18h; Size
0x140005e94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005e99  mov     rbx, rax
0x140005e9c  test    rax, rax
0x140005e9f  jz      loc_140005FDF
0x140005ea5  lea     rax, ??_7CWSHRemoteFactory@@6B@; const CWSHRemoteFactory::`vftable'
0x140005eac  mov     [rbx+10h], rsi
0x140005eb0  mov     [rbx], rax
0x140005eb3  mov     [rbx+8], r12d
0x140005eb7  call    cs:__imp_GetCurrentThreadId
0x140005ebd  xor     r9d, r9d; flags
0x140005ec0  mov     [rbx+0Ch], eax
0x140005ec3  mov     rdx, rbx; pUnk
0x140005ec6  lea     rcx, CLSID_WSHRemote; rclsid
0x140005ecd  lea     rax, [rbp+57h+dwRegister]
0x140005ed1  mov     [rsp+0C0h+lpdwRegister], rax; lpdwRegister
0x140005ed6  lea     r8d, [r9+14h]; dwClsContext
0x140005eda  call    cs:__imp_CoRegisterClassObject
0x140005ee0  mov     edi, eax
0x140005ee2  test    eax, eax
0x140005ee4  js      loc_140005FCE
0x140005eea  jmp     loc_140005FA3
0x140005eef  cmp     eax, 0FFFFFFFFh
0x140005ef2  jz      loc_140005FBD
0x140005ef8  mov     eax, [rbp+57h+Msg.message]
0x140005efb  sub     eax, 40Ah
0x140005f00  jz      short loc_140005F14
0x140005f02  cmp     eax, r12d
0x140005f05  jnz     loc_140005F99
0x140005f0b  mov     rcx, [rbp+57h+Msg.wParam]
0x140005f0f  mov     rax, [rcx]
0x140005f12  jmp     short loc_140005F90
0x140005f14  mov     rsi, [rbp+57h+Msg.wParam]
0x140005f18  xorps   xmm0, xmm0
0x140005f1b  mov     r14d, dword ptr [rbp+57h+Msg.lParam]
0x140005f1f  xor     edi, edi
0x140005f21  movdqu  [rbp+57h+var_70], xmm0
0x140005f26  mov     [rbp+57h+var_60], 0
0x140005f2e  mov     rcx, [rsi+rdi*8+0A8h]
0x140005f36  test    rcx, rcx
0x140005f39  jz      short loc_140005F81
0x140005f3b  mov     rax, [rcx]
0x140005f3e  lea     rdx, [rbp+57h+var_70]
0x140005f42  mov     [rsp+0C0h+var_80], 0
0x140005f4b  lea     r8, GUID_NULL
0x140005f52  mov     [rsp+0C0h+var_88], 0
0x140005f5b  mov     r9d, 400h
0x140005f61  mov     [rsp+0C0h+var_90], 0
0x140005f6a  mov     rax, [rax+30h]
0x140005f6e  mov     [rsp+0C0h+var_98], rdx
0x140005f73  mov     edx, r14d
0x140005f76  mov     word ptr [rsp+0C0h+lpdwRegister], r12w
0x140005f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f81  add     rdi, r12
0x140005f84  cmp     rdi, 32h ; '2'
0x140005f88  jnz     short loc_140005F2E
0x140005f8a  mov     rax, [rsi]
0x140005f8d  mov     rcx, rsi
0x140005f90  mov     rax, [rax+10h]
0x140005f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f99  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005f9d  call    cs:__imp_DispatchMessageA
0x140005fa3  xor     r9d, r9d; wMsgFilterMax
0x140005fa6  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140005faa  xor     r8d, r8d; wMsgFilterMin
0x140005fad  xor     edx, edx; hWnd
0x140005faf  call    cs:__imp_GetMessageA
0x140005fb5  test    eax, eax
0x140005fb7  jnz     loc_140005EEF
0x140005fbd  mov     ecx, [rbp+57h+dwRegister]; dwRegister
0x140005fc0  call    cs:__imp_CoRevokeClassObject
0x140005fc6  mov     edi, eax
0x140005fc8  test    eax, eax
0x140005fca  js      short loc_140005FCE
0x140005fcc  xor     edi, edi
0x140005fce  mov     rax, [rbx]
0x140005fd1  mov     rcx, rbx
0x140005fd4  mov     rax, [rax+10h]
0x140005fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fdd  jmp     short loc_140005FE4
0x140005fdf  mov     edi, 8007000Eh
0x140005fe4  mov     rbx, [rsp+0C0h+arg_0]
0x140005fec  mov     eax, edi
0x140005fee  add     rsp, 0A0h
0x140005ff5  pop     r14
0x140005ff7  pop     r12
0x140005ff9  pop     rdi
0x140005ffa  pop     rsi
0x140005ffb  pop     rbp
0x140005ffc  retn
```
