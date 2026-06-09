# NotificationThread(void *)

- ea: `0x1800027e0`
- end: `0x180002d8b`
- name: `?NotificationThread@@YAKPEAX@Z`
- size: `1451`
- prototype: `unsigned int __fastcall(struct _WLIDNotifyParam *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update`

## callees

- `0x1800027e0`
- `0x180002d94`
- `0x180003360`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000e3dc`
- `0x180013434`
- `0x180014db0`
- `0x180017710`
- `0x18001a0d0`
- `0x180048ff8`
- `0x180049340`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002c3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002d4d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002d62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002c3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002d4d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002d62`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180002906`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180002a59`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180002bd1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180002906`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180002a59`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180002bd1`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800029bc`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002c95`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800029bc`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d16`

## string_xrefs

- `0x180002929`: `WaitForMultipleObjects(hServiceStartedEvent+unadvise) termiated with %d`
- `0x180002bf4`: `WaitForMultipleObjects(hServiceStartedEvent+unadvise) termiated with %d`
- `0x18000284f`: `NotificationThread`
- `0x180002b27`: `Calling IdentityUpdated(0x%x, %s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NotificationThread(struct _WLIDNotifyParam *a1)
{
  const unsigned __int16 *v2; // rcx
  unsigned int v3; // r8d
  unsigned int v4; // r9d
  _BYTE *v5; // rdx
  DWORD v6; // eax
  signed int LastError; // eax
  const unsigned __int16 *v8; // rcx
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  signed int v11; // eax
  DWORD v12; // eax
  int v13; // eax
  const unsigned __int16 *v14; // rsi
  _WLIDNotifyParam *v15; // r14
  DWORD v16; // eax
  unsigned int v17; // edi
  _BYTE v19[32]; // [rsp+0h] [rbp-118h] BYREF
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int v21; // [rsp+30h] [rbp-E8h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-E4h] BYREF
  void *ContextHandle; // [rsp+38h] [rbp-E0h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-D8h] BYREF
  LPCWSTR lpName; // [rsp+48h] [rbp-D0h] BYREF
  void *Block; // [rsp+50h] [rbp-C8h] BYREF
  HANDLE v27; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD v28[4]; // [rsp+60h] [rbp-B8h] BYREF
  HANDLE v29; // [rsp+80h] [rbp-98h] BYREF
  _WLIDNotifyParam *v30; // [rsp+88h] [rbp-90h]
  HANDLE Handles[2]; // [rsp+90h] [rbp-88h] BYREF
  int v32; // [rsp+A0h] [rbp-78h] BYREF
  CPassportException *v33; // [rsp+A8h] [rbp-70h] BYREF
  ATL::CAtlException *v34; // [rsp+B0h] [rbp-68h] BYREF
  const wil::ResultException *v35; // [rsp+B8h] [rbp-60h] BYREF
  __int128 hObject; // [rsp+C0h] [rbp-58h] BYREF
  HANDLE v37; // [rsp+D0h] [rbp-48h]

  v21 = 0;
  lpName = 0;
  v30 = a1;
  ContextHandle = 0;
  hObject = 0;
  v37 = 0;
  v22 = 0;
  Block = 0;
  v24 = 0;
  v27 = 0;
  v29 = 0;
  *(_OWORD *)Handles = 0;
  v28[0] = "NotificationThread";
  v28[1] = &v21;
  v28[2] = 0;
  v28[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "NotificationThread",
    (const char *)0xC9F,
    0,
    *(const unsigned __int16 **)bAlertable);
  if ( !a1 )
  {
    v21 = -2147024809;
    CTraceFuncW<long>::~CTraceFuncW<long>(v28);
    goto LABEL_75;
  }
  v21 = CWLIDCCHelper::CreateEventExW(v2, L"Global\\{c245290c-487c-4f81-9aba-7eb0dac882a2}", v3, v4, &v27);
  if ( v21 < 0
    || (Handles[0] = v27,
        Handles[1] = *((HANDLE *)a1 + 3),
        v6 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0),
        v6 == 1) )
  {
    CTraceFuncW<long>::~CTraceFuncW<long>(v28);
    goto LABEL_75;
  }
  if ( v6 )
  {
    bAlertable[0] = v6;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0xCBFu,
      L"WaitForMultipleObjects(hServiceStartedEvent+unadvise) termiated with %d",
      *(_QWORD *)bAlertable);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v21 = LastError;
    CTraceFuncW<long>::~CTraceFuncW<long>(v28);
    goto LABEL_75;
  }
  try
  {
    v21 = NotifyKeyChangeIfAlreadyCached(a1);
    if ( v21 >= 0 )
    {
      v21 = WLIDCNCreateContext(*(_DWORD *)a1, (unsigned __int16 **)&lpName, &ContextHandle);
      if ( v21 >= 0 )
      {
        *(_QWORD *)&hObject = OpenEventW(0x100000u, 0, lpName);
        if ( !(_QWORD)hObject )
        {
          v11 = GetLastError();
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
LABEL_15:
          v21 = v11;
          CTraceFuncW<long>::~CTraceFuncW<long>(v28);
          goto LABEL_75;
        }
        *((_QWORD *)&hObject + 1) = *((_QWORD *)a1 + 3);
        v21 = CWLIDCCHelper::CreateEventExW(v8, L"Global\\{44ea083b-899c-4440-8338-2469fd4681cf}", v9, v10, &v29);
        if ( v21 >= 0 )
        {
          v37 = v29;
          do
          {
            while ( 1 )
            {
              v12 = WaitForMultipleObjectsEx(3u, (const HANDLE *)&hObject, 0, 0xFFFFFFFF, 0);
              if ( v12 )
                break;
              CMIDLPtr<unsigned short *>::Clear(&Block);
              v24 = 0;
              v22 = 0;
              v13 = WLIDCNGetNextNotification(ContextHandle, &v22, &v24, (unsigned __int8 **)&Block);
              v21 = v13;
              if ( v13 < 0 )
              {
                bAlertable[0] = v13;
                TracePrintW(
                  2u,
                  "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                  0xD05u,
                  L"WLIDCNGetNextNotification failed %#x. Aborting identity notification.",
                  *(_QWORD *)bAlertable);
                CTraceFuncW<long>::~CTraceFuncW<long>(v28);
                goto LABEL_75;
              }
              if ( v13 == 1 )
              {
                TracePrintW(
                  5u,
                  "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                  0xD0Bu,
                  L"WLIDCNGetNextNotification returned none");
              }
              else if ( (v24 & 1) != 0
                     || v24 < 2
                     || (v14 = (const unsigned __int16 *)Block, *((_WORD *)Block + ((unsigned __int64)v24 >> 1) - 1)) )
              {
                bAlertable[0] = v24;
                TracePrintW(
                  2u,
                  "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                  0xD15u,
                  L"WLIDCNGetNextNotification returned invalid string (size=%u bytes)",
                  *(_QWORD *)bAlertable);
              }
              else
              {
                v15 = v30;
                if ( *((_QWORD *)v30 + 1) )
                {
                  bAlertable[0] = v22;
                  TracePrintW(
                    5u,
                    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                    0xD1Bu,
                    L"Calling IdentityUpdated(0x%x, %s)",
                    *(_QWORD *)bAlertable,
                    Block);
                  (*(void (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *))(**((_QWORD **)v15 + 1) + 24LL))(
                    *((_QWORD *)v15 + 1),
                    v22,
                    v14);
                }
                if ( *(_DWORD *)a1 == 256 )
                  NotifyKeyChange(v14, *((struct IKeyAdviseSink **)v15 + 2));
              }
            }
            if ( v12 != 2 )
              goto LABEL_40;
            Handles[0] = v27;
            Handles[1] = *((HANDLE *)a1 + 3);
            v16 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
            if ( v16 == 1 )
              goto LABEL_40;
            if ( v16 )
            {
              bAlertable[0] = v16;
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                0xD43u,
                L"WaitForMultipleObjects(hServiceStartedEvent+unadvise) termiated with %d",
                *(_QWORD *)bAlertable);
              CTraceFuncW<long>::~CTraceFuncW<long>(v28);
              goto LABEL_75;
            }
            if ( ContextHandle )
            {
              WLIDCNDeleteContext(&ContextHandle);
              ContextHandle = 0;
            }
            if ( lpName )
            {
              free((void *)lpName);
              lpName = 0;
            }
            v21 = WLIDCNCreateContext(*(_DWORD *)a1, (unsigned __int16 **)&lpName, &ContextHandle);
            if ( v21 < 0 )
              goto LABEL_40;
            if ( (_QWORD)hObject )
            {
              CloseHandle((HANDLE)hObject);
              *(_QWORD *)&hObject = 0;
            }
            *(_QWORD *)&hObject = OpenEventW(0x100000u, 0, lpName);
          }
          while ( (_QWORD)hObject );
          v11 = GetLastError();
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
          goto LABEL_15;
        }
      }
    }
LABEL_40:
    CTraceFuncW<long>::~CTraceFuncW<long>(v28);
  }
  catch ( CPassportException *v33 )
  {
    v5 = v19;
    v21 = *((_DWORD *)v33 + 2);
    if ( v21 >= 0 )
      v21 = -2147418113;
  }
  catch ( ATL::CAtlException *v34 )
  {
    v5 = v19;
    v21 = *(_DWORD *)v34;
    if ( v21 >= 0 )
      v21 = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    v5 = v19;
    v21 = -2147024882;
  }
  catch ( long v32 )
  {
    v5 = v19;
    v21 = v32;
    if ( v32 >= 0 )
      v21 = -2147418113;
  }
  catch ( const wil::ResultException *v35 )
  {
    v5 = v19;
    v21 = *((_DWORD *)v35 + 8);
    if ( v21 >= 0 )
      v21 = -2147418113;
  }
LABEL_75:
  if ( (_QWORD)hObject )
    CloseHandle((HANDLE)hObject);
  if ( v29 )
    CloseHandle(v29);
  if ( v27 )
    CloseHandle(v27);
  if ( ContextHandle )
    WLIDCNDeleteContext(&ContextHandle);
  if ( v30 )
    _WLIDNotifyParam::`scalar deleting destructor'(v30, (unsigned int)v5);
  v17 = v21;
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  if ( lpName )
    free((void *)lpName);
  return v17;
}

```

## disassembly

```asm
0x1800027e0  mov     r11, rsp
0x1800027e3  push    rbx
0x1800027e4  push    rsi
0x1800027e5  push    rdi
0x1800027e6  push    r12
0x1800027e8  push    r14
0x1800027ea  push    r15
0x1800027ec  sub     rsp, 0E8h
0x1800027f3  mov     rax, cs:__security_cookie
0x1800027fa  xor     rax, rsp
0x1800027fd  mov     [rsp+118h+var_40], rax
0x180002805  mov     rdi, rcx
0x180002808  xor     ebx, ebx
0x18000280a  mov     [rsp+118h+var_E8], ebx
0x18000280e  mov     [rsp+118h+lpName], rbx
0x180002813  mov     [rsp+118h+var_90], rcx
0x18000281b  mov     [rsp+118h+ContextHandle], rbx
0x180002820  xorps   xmm0, xmm0
0x180002823  xor     eax, eax
0x180002825  movups  xmmword ptr [r11-58h], xmm0
0x18000282a  mov     [r11-48h], rax
0x18000282e  mov     [rsp+118h+var_E4], ebx
0x180002832  mov     [rsp+118h+Block], rbx
0x180002837  mov     [rsp+118h+var_D8], ebx
0x18000283b  mov     [rsp+118h+var_C0], rbx
0x180002840  mov     [r11-98h], rbx
0x180002847  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18000284f  lea     rdx, aNotificationth; "NotificationThread"
0x180002856  mov     [rsp+118h+var_B8], rdx
0x18000285b  lea     rax, [rsp+118h+var_E8]
0x180002860  mov     [rsp+118h+var_B0], rax
0x180002865  mov     [rsp+118h+var_A8], rbx
0x18000286a  mov     [rsp+118h+var_A0], rbx
0x18000286f  xor     r9d, r9d; unsigned int
0x180002872  mov     r8d, 0C9Fh; char *
0x180002878  lea     r12, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000287f  mov     rcx, r12; this
0x180002882  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180002887  nop
0x180002888  test    rdi, rdi
0x18000288b  jnz     short loc_1800028A5
0x18000288d  mov     [rsp+118h+var_E8], 80070057h
0x180002895  lea     rcx, [rsp+118h+var_B8]
0x18000289a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000289f  nop
0x1800028a0  jmp     loc_180002CE6
0x1800028a5  lea     rax, [rsp+118h+var_C0]
0x1800028aa  mov     qword ptr [rsp+118h+bAlertable], rax; void **
0x1800028af  lea     rdx, aGlobalC245290c; "Global\\{c245290c-487c-4f81-9aba-7eb0da"...
0x1800028b6  call    ?CreateEventExW@CWLIDCCHelper@@SAJPEBG0KKPEAPEAX@Z; CWLIDCCHelper::CreateEventExW(ushort const *,ushort const *,ulong,ulong,void * *)
0x1800028bb  mov     [rsp+118h+var_E8], eax
0x1800028bf  test    eax, eax
0x1800028c1  jns     short loc_1800028D3
0x1800028c3  lea     rcx, [rsp+118h+var_B8]
0x1800028c8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800028cd  nop
0x1800028ce  jmp     loc_180002CE6
0x1800028d3  mov     rax, [rsp+118h+var_C0]
0x1800028d8  mov     [rsp+118h+Handles], rax
0x1800028e0  mov     rax, [rdi+18h]
0x1800028e4  mov     [rsp+118h+Handles+8], rax
0x1800028ec  mov     [rsp+118h+bAlertable], ebx; bAlertable
0x1800028f0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800028f4  xor     r8d, r8d; bWaitAll
0x1800028f7  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800028ff  lea     r15d, [r8+2]
0x180002903  mov     ecx, r15d; nCount
0x180002906  call    cs:__imp_WaitForMultipleObjectsEx
0x18000290c  cmp     eax, 1
0x18000290f  jnz     short loc_180002921
0x180002911  lea     rcx, [rsp+118h+var_B8]
0x180002916  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000291b  nop
0x18000291c  jmp     loc_180002CE6
0x180002921  test    eax, eax
0x180002923  jz      short loc_180002967
0x180002925  mov     [rsp+118h+bAlertable], eax
0x180002929  lea     r9, aWaitformultipl; "WaitForMultipleObjects(hServiceStartedE"...
0x180002930  mov     r8d, 0CBFh; unsigned int
0x180002936  mov     rdx, r12; char *
0x180002939  mov     ecx, r15d; unsigned __int8
0x18000293c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180002941  call    cs:__imp_GetLastError
0x180002947  test    eax, eax
0x180002949  jle     short loc_180002953
0x18000294b  movzx   eax, ax
0x18000294e  or      eax, 80070000h
0x180002953  mov     [rsp+118h+var_E8], eax
0x180002957  lea     rcx, [rsp+118h+var_B8]
0x18000295c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002961  nop
0x180002962  jmp     loc_180002CE6
0x180002967  mov     rcx, rdi; struct _WLIDNotifyParam *
0x18000296a  call    ?NotifyKeyChangeIfAlreadyCached@@YAJQEAU_WLIDNotifyParam@@@Z; NotifyKeyChangeIfAlreadyCached(_WLIDNotifyParam * const)
0x18000296f  mov     [rsp+118h+var_E8], eax
0x180002973  test    eax, eax
0x180002975  jns     short loc_180002987
0x180002977  lea     rcx, [rsp+118h+var_B8]
0x18000297c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002981  nop
0x180002982  jmp     loc_180002CE6
0x180002987  lea     r8, [rsp+118h+ContextHandle]; void **
0x18000298c  lea     rdx, [rsp+118h+lpName]; unsigned __int16 **
0x180002991  mov     ecx, [rdi]; unsigned int
0x180002993  call    ?WLIDCNCreateContext@@YAJKPEAPEAGPEAPEAX@Z; WLIDCNCreateContext(ulong,ushort * *,void * *)
0x180002998  mov     [rsp+118h+var_E8], eax
0x18000299c  test    eax, eax
0x18000299e  jns     short loc_1800029B0
0x1800029a0  lea     rcx, [rsp+118h+var_B8]
0x1800029a5  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800029aa  nop
0x1800029ab  jmp     loc_180002CE6
0x1800029b0  mov     r8, [rsp+118h+lpName]; lpName
0x1800029b5  xor     edx, edx; bInheritHandle
0x1800029b7  mov     ecx, 100000h; dwDesiredAccess
0x1800029bc  call    cs:__imp_OpenEventW
0x1800029c2  mov     [rsp+118h+hObject], rax
0x1800029ca  test    rax, rax
0x1800029cd  jnz     short loc_1800029F5
0x1800029cf  call    cs:__imp_GetLastError
0x1800029d5  test    eax, eax
0x1800029d7  jle     short loc_1800029E1
0x1800029d9  movzx   eax, ax
0x1800029dc  or      eax, 80070000h
0x1800029e1  mov     [rsp+118h+var_E8], eax
0x1800029e5  lea     rcx, [rsp+118h+var_B8]
0x1800029ea  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800029ef  nop
0x1800029f0  jmp     loc_180002CE6
0x1800029f5  mov     rax, [rdi+18h]
0x1800029f9  mov     [rsp+118h+var_50], rax
0x180002a01  lea     rax, [rsp+118h+var_98]
0x180002a09  mov     qword ptr [rsp+118h+bAlertable], rax; void **
0x180002a0e  lea     rdx, aGlobal44ea083b; "Global\\{44ea083b-899c-4440-8338-2469fd"...
0x180002a15  call    ?CreateEventExW@CWLIDCCHelper@@SAJPEBG0KKPEAPEAX@Z; CWLIDCCHelper::CreateEventExW(ushort const *,ushort const *,ulong,ulong,void * *)
0x180002a1a  mov     [rsp+118h+var_E8], eax
0x180002a1e  test    eax, eax
0x180002a20  jns     short loc_180002A32
0x180002a22  lea     rcx, [rsp+118h+var_B8]
0x180002a27  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002a2c  nop
0x180002a2d  jmp     loc_180002CE6
0x180002a32  mov     rax, [rsp+118h+var_98]
0x180002a3a  mov     [rsp+118h+var_48], rax
0x180002a42  mov     [rsp+118h+bAlertable], ebx; bAlertable
0x180002a46  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180002a4a  xor     r8d, r8d; bWaitAll
0x180002a4d  lea     rdx, [rsp+118h+hObject]; lpHandles
0x180002a55  lea     ecx, [r8+3]; nCount
0x180002a59  call    cs:__imp_WaitForMultipleObjectsEx
0x180002a5f  test    eax, eax
0x180002a61  jnz     loc_180002B99
0x180002a67  lea     rcx, [rsp+118h+Block]
0x180002a6c  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180002a71  mov     [rsp+118h+var_D8], ebx
0x180002a75  mov     [rsp+118h+var_E4], ebx
0x180002a79  lea     r9, [rsp+118h+Block]; unsigned __int8 **
0x180002a7e  lea     r8, [rsp+118h+var_D8]; unsigned int *
0x180002a83  lea     rdx, [rsp+118h+var_E4]; unsigned int *
0x180002a88  mov     rcx, [rsp+118h+ContextHandle]; void *
0x180002a8d  call    ?WLIDCNGetNextNotification@@YAJPEAXPEAK1PEAPEAE@Z; WLIDCNGetNextNotification(void *,ulong *,ulong *,uchar * *)
0x180002a92  mov     [rsp+118h+var_E8], eax
0x180002a96  test    eax, eax
0x180002a98  jns     short loc_180002AC7
0x180002a9a  mov     [rsp+118h+bAlertable], eax
0x180002a9e  lea     r9, aWlidcngetnextn_2; "WLIDCNGetNextNotification failed %#x. A"...
0x180002aa5  mov     r8d, 0D05h; unsigned int
0x180002aab  mov     rdx, r12; char *
0x180002aae  mov     ecx, r15d; unsigned __int8
0x180002ab1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180002ab6  nop
0x180002ab7  lea     rcx, [rsp+118h+var_B8]
0x180002abc  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002ac1  nop
0x180002ac2  jmp     loc_180002CE6
0x180002ac7  cmp     eax, 1
0x180002aca  jnz     short loc_180002AE9
0x180002acc  lea     r9, aWlidcngetnextn; "WLIDCNGetNextNotification returned none"
0x180002ad3  mov     r8d, 0D0Bh; unsigned int
0x180002ad9  mov     rdx, r12; char *
0x180002adc  lea     ecx, [rax+4]; unsigned __int8
0x180002adf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180002ae4  jmp     loc_180002A42
0x180002ae9  mov     ecx, [rsp+118h+var_D8]
0x180002aed  test    cl, 1
0x180002af0  jnz     loc_180002B78
0x180002af6  cmp     ecx, r15d
0x180002af9  jb      short loc_180002B78
0x180002afb  mov     rsi, [rsp+118h+Block]
0x180002b00  mov     eax, ecx
0x180002b02  shr     rax, 1
0x180002b05  cmp     [rsi+rax*2-2], bx
0x180002b0a  jnz     short loc_180002B78
0x180002b0c  mov     r14, [rsp+118h+var_90]
0x180002b14  cmp     [r14+8], rbx
0x180002b18  jz      short loc_180002B58
0x180002b1a  mov     [rsp+118h+var_F0], rsi
0x180002b1f  mov     eax, [rsp+118h+var_E4]
0x180002b23  mov     [rsp+118h+bAlertable], eax
0x180002b27  lea     r9, aCallingIdentit; "Calling IdentityUpdated(0x%x, %s)"
0x180002b2e  mov     r8d, 0D1Bh; unsigned int
0x180002b34  mov     rdx, r12; char *
0x180002b37  mov     ecx, 5; unsigned __int8
0x180002b3c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180002b41  mov     rcx, [r14+8]
0x180002b45  mov     rax, [rcx]
0x180002b48  mov     r8, rsi
0x180002b4b  mov     edx, [rsp+118h+var_E4]
0x180002b4f  mov     rax, [rax+18h]
0x180002b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b58  cmp     dword ptr [rdi], 100h
0x180002b5e  jnz     loc_180002A42
0x180002b64  mov     rdx, r14
0x180002b67  mov     rdx, [rdx+10h]; struct IKeyAdviseSink *
0x180002b6b  mov     rcx, rsi; unsigned __int16 *
0x180002b6e  call    ?NotifyKeyChange@@YAJPEBGPEAUIKeyAdviseSink@@@Z; NotifyKeyChange(ushort const *,IKeyAdviseSink *)
0x180002b73  jmp     loc_180002A42
0x180002b78  mov     [rsp+118h+bAlertable], ecx
0x180002b7c  lea     r9, aWlidcngetnextn_0; "WLIDCNGetNextNotification returned inva"...
0x180002b83  mov     r8d, 0D15h; unsigned int
0x180002b89  mov     rdx, r12; char *
0x180002b8c  mov     ecx, r15d; unsigned __int8
0x180002b8f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180002b94  jmp     loc_180002A42
0x180002b99  cmp     eax, r15d
0x180002b9c  jnz     loc_180002CCF
0x180002ba2  mov     rax, [rsp+118h+var_C0]
0x180002ba7  mov     [rsp+118h+Handles], rax
0x180002baf  mov     rax, [rdi+18h]
0x180002bb3  mov     [rsp+118h+Handles+8], rax
0x180002bbb  mov     [rsp+118h+bAlertable], ebx; bAlertable
0x180002bbf  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180002bc3  xor     r8d, r8d; bWaitAll
0x180002bc6  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180002bce  mov     ecx, r15d; nCount
0x180002bd1  call    cs:__imp_WaitForMultipleObjectsEx
0x180002bd7  cmp     eax, 1
0x180002bda  jnz     short loc_180002BEC
0x180002bdc  lea     rcx, [rsp+118h+var_B8]
0x180002be1  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002be6  nop
0x180002be7  jmp     loc_180002CE6
0x180002bec  test    eax, eax
0x180002bee  jz      short loc_180002C1D
0x180002bf0  mov     [rsp+118h+bAlertable], eax
0x180002bf4  lea     r9, aWaitformultipl; "WaitForMultipleObjects(hServiceStartedE"...
0x180002bfb  mov     r8d, 0D43h; unsigned int
0x180002c01  mov     rdx, r12; char *
0x180002c04  mov     ecx, r15d; unsigned __int8
0x180002c07  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180002c0c  nop
0x180002c0d  lea     rcx, [rsp+118h+var_B8]
0x180002c12  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002c17  nop
0x180002c18  jmp     loc_180002CE6
0x180002c1d  cmp     [rsp+118h+ContextHandle], rbx
0x180002c22  jz      short loc_180002C33
0x180002c24  lea     rcx, [rsp+118h+ContextHandle]; ContextHandle
0x180002c29  call    ?WLIDCNDeleteContext@@YAJPEAPEAX@Z; WLIDCNDeleteContext(void * *)
0x180002c2e  mov     [rsp+118h+ContextHandle], rbx
0x180002c33  mov     rcx, [rsp+118h+lpName]; Block
0x180002c38  test    rcx, rcx
0x180002c3b  jz      short loc_180002C48
0x180002c3d  call    cs:__imp_free
0x180002c43  mov     [rsp+118h+lpName], rbx
0x180002c48  lea     r8, [rsp+118h+ContextHandle]; void **
0x180002c4d  lea     rdx, [rsp+118h+lpName]; unsigned __int16 **
0x180002c52  mov     ecx, [rdi]; unsigned int
0x180002c54  call    ?WLIDCNCreateContext@@YAJKPEAPEAGPEAPEAX@Z; WLIDCNCreateContext(ulong,ushort * *,void * *)
0x180002c59  mov     [rsp+118h+var_E8], eax
0x180002c5d  test    eax, eax
0x180002c5f  jns     short loc_180002C6E
0x180002c61  lea     rcx, [rsp+118h+var_B8]
0x180002c66  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002c6b  nop
0x180002c6c  jmp     short loc_180002CE6
0x180002c6e  mov     rcx, [rsp+118h+hObject]; hObject
0x180002c76  test    rcx, rcx
0x180002c79  jz      short loc_180002C89
0x180002c7b  call    cs:__imp_CloseHandle
0x180002c81  mov     [rsp+118h+hObject], rbx
0x180002c89  mov     r8, [rsp+118h+lpName]; lpName
0x180002c8e  xor     edx, edx; bInheritHandle
0x180002c90  mov     ecx, 100000h; dwDesiredAccess
0x180002c95  call    cs:__imp_OpenEventW
0x180002c9b  mov     [rsp+118h+hObject], rax
0x180002ca3  test    rax, rax
0x180002ca6  jnz     loc_180002A42
0x180002cac  call    cs:__imp_GetLastError
0x180002cb2  test    eax, eax
0x180002cb4  jle     short loc_180002CBE
0x180002cb6  movzx   eax, ax
0x180002cb9  or      eax, 80070000h
0x180002cbe  mov     [rsp+118h+var_E8], eax
0x180002cc2  lea     rcx, [rsp+118h+var_B8]
0x180002cc7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180002ccc  nop
0x180002ccd  jmp     short loc_180002CE6
0x180002ccf  lea     rcx, [rsp+118h+var_B8]
0x180002cd4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
  ... truncated ...
```
