# CreateLocationsForSearchRootWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180021ac0`
- end: `0x180021c36`
- name: `?CreateLocationsForSearchRootWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `374`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, HANDLE *, struct _TP_WORK *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005cc0`
- `0x180021878`
- `0x180021ac0`
- `0x180022f90`
- `0x1800231a4`
- `0x180023940`
- `0x180023f48`
- `0x1800240ec`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180021b73`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180021b73`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021b12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021b12`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021be2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021be2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021bec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021bec`

## string_xrefs

- `0x180021bb4`: `SavePath`

## pseudocode

```c
void __fastcall CreateLocationsForSearchRootWorker(
        struct _TP_CALLBACK_INSTANCE *a1,
        HANDLE *a2,
        struct _TP_WORK *a3,
        int a4)
{
  int v5; // ebp
  signed int v6; // eax
  struct _TP_CALLBACK_INSTANCE *v7; // rcx
  bool v8; // sf
  int v9; // edx
  HRESULT Instance; // eax
  unsigned int v11; // edx
  CPHLocationTemplateProcessor *v12; // rsi
  __int64 v13; // rdi
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  struct ILibraryFactory *ppv; // [rsp+30h] [rbp-48h] BYREF
  CPHLocationTemplateProcessor *v18[2]; // [rsp+38h] [rbp-40h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)a1,
      (unsigned int)PHLocationCreator_CreateSearchRootLocations_Start,
      (_DWORD)a3,
      a4,
      (__int64)v18);
  v5 = SHCoInitialize();
  if ( v5 >= 0 )
  {
    v6 = WaitForSingleObject(a2[3], 0x2710u);
    v8 = v6 < 0;
    if ( v6 > 0 )
      v8 = 1;
    if ( !v8 )
    {
      v9 = *((_DWORD *)a2 + 4);
      v18[0] = 0;
      if ( (int)CPHLocationTemplateProcessor::s_LoadTemplatesForSearchRoot(v7, v9, 0, v18) >= 0 )
      {
        ppv = 0;
        Instance = SHCoCreateInstance(
                     0,
                     &CLSID_LibraryFactory,
                     0,
                     &GUID_12929ca2_37e4_440a_815a_759d7df24ec6,
                     (void **)&ppv);
        v12 = v18[0];
        if ( Instance >= 0 )
        {
          v13 = *((_QWORD *)v18[0] + 68);
          if ( v13
            && (int)CLocationTemplate::_CreateLocationFile(
                      *((CLocationTemplate **)v18[0] + 68),
                      ppv,
                      *((struct IShellItem **)v18[0] + 67)) >= 0 )
          {
            RegSetStringValue(*(HKEY *)(v13 + 1064), L"SavePath", (const unsigned __int16 *)(v13 + 540));
          }
          (*(void (__fastcall **)(struct ILibraryFactory *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( v12 )
          CPHLocationTemplateProcessor::`scalar deleting destructor'(v12, v11);
      }
      SetEvent(a2[4]);
    }
    if ( !v5 )
      CoUninitialize();
  }
  (*((void (__fastcall **)(HANDLE *))*a2 + 2))(a2);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v14,
      (unsigned int)PHLocationCreator_CreateSearchRootLocations_Stop,
      v15,
      v16,
      (__int64)v18);
}

```

## disassembly

```asm
0x180021ac0  push    rbx
0x180021ac2  push    rbp
0x180021ac3  push    rsi
0x180021ac4  push    rdi
0x180021ac5  sub     rsp, 58h
0x180021ac9  mov     rax, cs:__security_cookie
0x180021ad0  xor     rax, rsp
0x180021ad3  mov     [rsp+78h+var_30], rax
0x180021ad8  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180021adf  mov     rbx, rdx
0x180021ae2  jz      short loc_180021AFA
0x180021ae4  lea     rax, [rsp+78h+var_40]
0x180021ae9  lea     rdx, PHLocationCreator_CreateSearchRootLocations_Start
0x180021af0  mov     [rsp+78h+ppv], rax
0x180021af5  call    McGenEventWrite_EtwEventWriteTransfer
0x180021afa  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180021aff  mov     ebp, eax
0x180021b01  test    eax, eax
0x180021b03  js      loc_180021BF2
0x180021b09  mov     rcx, [rbx+18h]; hHandle
0x180021b0d  mov     edx, 2710h; dwMilliseconds
0x180021b12  call    cs:__imp_WaitForSingleObject
0x180021b18  test    eax, eax
0x180021b1a  jle     short loc_180021B26
0x180021b1c  movzx   eax, ax
0x180021b1f  or      eax, 80070000h
0x180021b24  test    eax, eax
0x180021b26  js      loc_180021BE8
0x180021b2c  mov     edx, [rbx+10h]; int
0x180021b2f  lea     r9, [rsp+78h+var_40]; struct CPHLocationTemplateProcessor **
0x180021b34  xor     r8d, r8d; int
0x180021b37  mov     [rsp+78h+var_40], 0
0x180021b40  call    ?s_LoadTemplatesForSearchRoot@CPHLocationTemplateProcessor@@SAJPEAU_TP_CALLBACK_INSTANCE@@HHPEAPEAV1@@Z; CPHLocationTemplateProcessor::s_LoadTemplatesForSearchRoot(_TP_CALLBACK_INSTANCE *,int,int,CPHLocationTemplateProcessor * *)
0x180021b45  test    eax, eax
0x180021b47  js      loc_180021BDE
0x180021b4d  lea     rax, [rsp+78h+var_48]
0x180021b52  mov     [rsp+78h+var_48], 0
0x180021b5b  lea     r9, _GUID_12929ca2_37e4_440a_815a_759d7df24ec6; riid
0x180021b62  mov     [rsp+78h+ppv], rax; ppv
0x180021b67  xor     r8d, r8d; pUnkOuter
0x180021b6a  lea     rdx, CLSID_LibraryFactory; pclsid
0x180021b71  xor     ecx, ecx; pszCLSID
0x180021b73  call    cs:__imp_SHCoCreateInstance
0x180021b79  mov     rsi, [rsp+78h+var_40]
0x180021b7e  test    eax, eax
0x180021b80  js      short loc_180021BD1
0x180021b82  mov     rdi, [rsi+220h]
0x180021b89  test    rdi, rdi
0x180021b8c  jz      short loc_180021BC0
0x180021b8e  mov     r8, [rsi+218h]; struct IShellItem *
0x180021b95  mov     rcx, rdi; this
0x180021b98  mov     rdx, [rsp+78h+var_48]; struct ILibraryFactory *
0x180021b9d  call    ?_CreateLocationFile@CLocationTemplate@@AEAAJPEAUILibraryFactory@@PEAUIShellItem@@@Z; CLocationTemplate::_CreateLocationFile(ILibraryFactory *,IShellItem *)
0x180021ba2  test    eax, eax
0x180021ba4  js      short loc_180021BC0
0x180021ba6  mov     rcx, [rdi+428h]; HKEY
0x180021bad  lea     r8, [rdi+21Ch]; unsigned __int16 *
0x180021bb4  lea     rdx, aSavepath; "SavePath"
0x180021bbb  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEBG1@Z; RegSetStringValue(HKEY__ *,ushort const *,ushort const *)
0x180021bc0  mov     rcx, [rsp+78h+var_48]
0x180021bc5  mov     rax, [rcx]
0x180021bc8  mov     rax, [rax+10h]
0x180021bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bd1  test    rsi, rsi
0x180021bd4  jz      short loc_180021BDE
0x180021bd6  mov     rcx, rsi; this
0x180021bd9  call    ??_GCPHLocationTemplateProcessor@@QEAAPEAXI@Z; CPHLocationTemplateProcessor::`scalar deleting destructor'(uint)
0x180021bde  mov     rcx, [rbx+20h]; hEvent
0x180021be2  call    cs:__imp_SetEvent
0x180021be8  test    ebp, ebp
0x180021bea  jnz     short loc_180021BF2
0x180021bec  call    cs:__imp_CoUninitialize
0x180021bf2  mov     rax, [rbx]
0x180021bf5  mov     rcx, rbx
0x180021bf8  mov     rax, [rax+10h]
0x180021bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c01  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180021c08  jz      short loc_180021C20
0x180021c0a  lea     rax, [rsp+78h+var_40]
0x180021c0f  lea     rdx, PHLocationCreator_CreateSearchRootLocations_Stop
0x180021c16  mov     [rsp+78h+ppv], rax
0x180021c1b  call    McGenEventWrite_EtwEventWriteTransfer
0x180021c20  mov     rcx, [rsp+78h+var_30]
0x180021c25  xor     rcx, rsp; StackCookie
0x180021c28  call    __security_check_cookie
0x180021c2d  add     rsp, 58h
0x180021c31  pop     rdi
0x180021c32  pop     rsi
0x180021c33  pop     rbp
0x180021c34  pop     rbx
0x180021c35  retn
```
