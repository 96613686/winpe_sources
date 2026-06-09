# CbsClient::QueryProperties(void)

- ea: `0x14001150c`
- end: `0x1400117b9`
- name: `?QueryProperties@CbsClient@@AEAAJXZ`
- size: `685`
- prototype: `__int64 __fastcall(CbsClient *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140010e88`
- `0x140011190`

## callees

- `0x14000e280`
- `0x14000eb0c`
- `0x14001150c`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14001174a`
- `KERNEL32!LocalFree` at `0x14001175d`
- `KERNEL32!LocalFree` at `0x1400117a2`
- `KERNEL32!LocalFree` at `0x14001174a`
- `KERNEL32!LocalFree` at `0x14001175d`
- `KERNEL32!LocalFree` at `0x1400117a2`
- `msvcrt!_wcsicmp` at `0x1400115be`
- `msvcrt!_wcsicmp` at `0x140011652`
- `msvcrt!_wcsicmp` at `0x1400115be`
- `msvcrt!_wcsicmp` at `0x140011652`
- `ServicingCommon!SczAllocFromSz` at `0x1400116c9`
- `ServicingCommon!SczAllocFromSz` at `0x1400116e4`
- `ServicingCommon!SczAllocFromSz` at `0x1400116c9`
- `ServicingCommon!SczAllocFromSz` at `0x1400116e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011737`

## pseudocode

```c
__int64 __fastcall CbsClient::QueryProperties(CbsClient *this)
{
  __int64 v2; // rcx
  signed int Message; // ebx
  int v4; // ebx
  __int64 v5; // rdi
  char *v6; // rcx
  const wchar_t *v7; // r9
  __int64 v8; // rdx
  HLOCAL v9; // rdi
  wchar_t *String1; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL v12; // [rsp+38h] [rbp-8h] BYREF
  wchar_t *v13; // [rsp+80h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+48h] BYREF
  HLOCAL v15; // [rsp+90h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  v2 = *((_QWORD *)this + 1);
  pv = 0;
  String1 = 0;
  v15 = 0;
  v13 = 0;
  hMem = 0;
  Message = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v2 + 32LL))(v2, 1, (char *)this + 536);
  if ( Message >= 0 )
  {
    Message = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **))(**((_QWORD **)this + 1) + 32LL))(
                *((_QWORD *)this + 1),
                8,
                &String1);
    if ( Message < 0 )
    {
      WusaLogDebugEventA(L"CbsClient::QueryProperties", 404, "Failed to save package release type as string");
      goto LABEL_27;
    }
    v4 = 0;
    while ( 1 )
    {
      v5 = 2LL * v4;
      if ( !_wcsicmp(String1, (&off_1400160A0)[2 * v4]) )
        break;
      if ( (unsigned int)++v4 >= 9 )
        goto LABEL_9;
    }
    Message = WusaLoadMessage(*((_DWORD *)&off_1400160A0 + 4 * v4 + 2), (unsigned __int16 **)&v15);
    if ( Message < 0 )
    {
      WusaLogDebugEventA(
        L"CbsClient::QueryProperties",
        411,
        "Failed to get release type text, id %u",
        *((_DWORD *)&off_1400160A0 + 2 * v5 + 2));
      goto LABEL_27;
    }
LABEL_9:
    if ( !v15 )
    {
      Message = -2145124297;
      goto LABEL_27;
    }
    Message = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **))(**((_QWORD **)this + 1) + 32LL))(
                *((_QWORD *)this + 1),
                2,
                &v13);
    if ( Message < 0 )
    {
      WusaLogDebugEventA(L"CbsClient::QueryProperties", 424, "Failed to save package name as string");
      goto LABEL_27;
    }
    if ( !*v13 || !_wcsicmp(v13, L"default") )
    {
      Message = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 1) + 32LL))(
                  *((_QWORD *)this + 1),
                  7,
                  &pv);
      if ( Message < 0 )
      {
        WusaLogDebugEventA(L"CbsClient::QueryProperties", 430, "Failed to save package keyword as string");
        goto LABEL_27;
      }
      Message = WusaLoadMessage(0xEA73u, (unsigned __int16 **)&hMem, v15, pv);
      if ( Message < 0 )
      {
        WusaLogDebugEventA(L"CbsClient::QueryProperties", 433, "Failed to get STR_DISPLAY_NAME text");
        goto LABEL_27;
      }
    }
    v6 = (char *)this + 544;
    if ( hMem )
    {
      Message = SczAllocFromSz(v6, hMem);
      if ( Message >= 0 )
        goto LABEL_27;
      v7 = (const wchar_t *)hMem;
      v8 = 439;
    }
    else
    {
      Message = SczAllocFromSz(v6, v13);
      if ( Message >= 0 )
        goto LABEL_27;
      v7 = v13;
      v8 = 444;
    }
    WusaLogDebugEventA(L"CbsClient::QueryProperties", v8, "Failed to allocate display name for %S", v7);
  }
  else
  {
    WusaLogDebugEventA(L"CbsClient::QueryProperties", 401, "Failed to save package identity as string");
  }
LABEL_27:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v13 )
  {
    CoTaskMemFree(v13);
    v13 = 0;
  }
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v15 )
  {
    LocalFree(v15);
    v15 = 0;
  }
  if ( Message < 0 )
  {
    v12 = 0;
    WusaGetErrorMessage(Message, (unsigned __int16 **)&v12);
    v9 = v12;
    WusaLogDebugEventA(
      L"CbsClient::QueryProperties",
      455,
      "Exit with error code 0X%x (%ls)",
      Message,
      (const wchar_t *)v12);
    if ( v9 )
      LocalFree(v9);
  }
  return (unsigned int)Message;
}

```

## disassembly

```asm
0x14001150c  push    rbp
0x14001150e  push    rbx
0x14001150f  push    rsi
0x140011510  push    rdi
0x140011511  push    r12
0x140011513  push    r14
0x140011515  push    r15
0x140011517  mov     rbp, rsp
0x14001151a  sub     rsp, 40h
0x14001151e  xor     r14d, r14d
0x140011521  mov     rsi, rcx
0x140011524  mov     rcx, [rcx+8]
0x140011528  mov     [rbp+pv], r14
0x14001152c  mov     [rbp+String1], r14
0x140011530  mov     [rbp+arg_10], r14
0x140011534  lea     r8, [rsi+218h]
0x14001153b  mov     [rbp+arg_0], r14
0x14001153f  lea     edx, [r14+1]
0x140011543  mov     [rbp+hMem], r14
0x140011547  mov     rax, [rcx]
0x14001154a  mov     rax, [rax+20h]
0x14001154e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011553  lea     r15, aCbsclientQuery; "CbsClient::QueryProperties"
0x14001155a  mov     ebx, eax
0x14001155c  test    eax, eax
0x14001155e  jns     short loc_140011579
0x140011560  lea     r8, aFailedToSavePa_1; "Failed to save package identity as stri"...
0x140011567  mov     edx, 191h
0x14001156c  mov     rcx, r15
0x14001156f  call    WusaLogDebugEventA
0x140011574  jmp     loc_140011708
0x140011579  mov     rcx, [rsi+8]
0x14001157d  lea     r8, [rbp+String1]
0x140011581  mov     edx, 8
0x140011586  mov     rax, [rcx]
0x140011589  mov     rax, [rax+20h]
0x14001158d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011592  mov     ebx, eax
0x140011594  test    eax, eax
0x140011596  jns     short loc_1400115A6
0x140011598  lea     r8, aFailedToSavePa_0; "Failed to save package release type as "...
0x14001159f  mov     edx, 194h
0x1400115a4  jmp     short loc_14001156C
0x1400115a6  mov     ebx, r14d
0x1400115a9  lea     r12, off_1400160A0; "Critical Update"
0x1400115b0  mov     rcx, [rbp+String1]; String1
0x1400115b4  movsxd  rdi, ebx
0x1400115b7  add     rdi, rdi
0x1400115ba  mov     rdx, [r12+rdi*8]; String2
0x1400115be  call    cs:__imp__wcsicmp
0x1400115c4  test    eax, eax
0x1400115c6  jz      short loc_1400115DF
0x1400115c8  inc     ebx
0x1400115ca  cmp     ebx, 9
0x1400115cd  jb      short loc_1400115B0
0x1400115cf  cmp     [rbp+arg_10], r14
0x1400115d3  jnz     short loc_140011611
0x1400115d5  mov     ebx, 80240037h
0x1400115da  jmp     loc_140011708
0x1400115df  mov     ecx, [r12+rdi*8+8]; dwMessageId
0x1400115e4  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x1400115e8  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x1400115ed  mov     ebx, eax
0x1400115ef  test    eax, eax
0x1400115f1  jns     short loc_1400115CF
0x1400115f3  mov     r9d, [r12+rdi*8+8]
0x1400115f8  lea     r8, aFailedToGetRel; "Failed to get release type text, id %u"
0x1400115ff  mov     edx, 19Bh
0x140011604  mov     rcx, r15
0x140011607  call    WusaLogDebugEventA
0x14001160c  jmp     loc_140011708
0x140011611  mov     rcx, [rsi+8]
0x140011615  lea     r8, [rbp+arg_0]
0x140011619  mov     edx, 2
0x14001161e  mov     rax, [rcx]
0x140011621  mov     rax, [rax+20h]
0x140011625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001162a  mov     ebx, eax
0x14001162c  test    eax, eax
0x14001162e  jns     short loc_140011641
0x140011630  lea     r8, aFailedToSavePa_2; "Failed to save package name as string"
0x140011637  mov     edx, 1A8h
0x14001163c  jmp     loc_14001156C
0x140011641  mov     rcx, [rbp+arg_0]; String1
0x140011645  cmp     [rcx], r14w
0x140011649  jz      short loc_14001165C
0x14001164b  lea     rdx, aDefault; "default"
0x140011652  call    cs:__imp__wcsicmp
0x140011658  test    eax, eax
0x14001165a  jnz     short loc_1400116B9
0x14001165c  mov     rcx, [rsi+8]
0x140011660  lea     r8, [rbp+pv]
0x140011664  mov     edx, 7
0x140011669  mov     rax, [rcx]
0x14001166c  mov     rax, [rax+20h]
0x140011670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011675  mov     ebx, eax
0x140011677  test    eax, eax
0x140011679  jns     short loc_14001168C
0x14001167b  lea     r8, aFailedToSavePa; "Failed to save package keyword as strin"...
0x140011682  mov     edx, 1AEh
0x140011687  jmp     loc_14001156C
0x14001168c  mov     r9, [rbp+pv]
0x140011690  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x140011694  mov     r8, [rbp+arg_10]
0x140011698  mov     ecx, 0EA73h; dwMessageId
0x14001169d  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x1400116a2  mov     ebx, eax
0x1400116a4  test    eax, eax
0x1400116a6  jns     short loc_1400116B9
0x1400116a8  lea     r8, aFailedToGetStr; "Failed to get STR_DISPLAY_NAME text"
0x1400116af  mov     edx, 1B1h
0x1400116b4  jmp     loc_14001156C
0x1400116b9  mov     rdx, [rbp+hMem]
0x1400116bd  lea     rcx, [rsi+220h]
0x1400116c4  test    rdx, rdx
0x1400116c7  jz      short loc_1400116E0
0x1400116c9  call    cs:__imp_SczAllocFromSz
0x1400116cf  mov     ebx, eax
0x1400116d1  test    eax, eax
0x1400116d3  jns     short loc_140011708
0x1400116d5  mov     r9, [rbp+hMem]
0x1400116d9  mov     edx, 1B7h
0x1400116de  jmp     short loc_1400116F9
0x1400116e0  mov     rdx, [rbp+arg_0]
0x1400116e4  call    cs:__imp_SczAllocFromSz
0x1400116ea  mov     ebx, eax
0x1400116ec  test    eax, eax
0x1400116ee  jns     short loc_140011708
0x1400116f0  mov     r9, [rbp+arg_0]
0x1400116f4  mov     edx, 1BCh
0x1400116f9  lea     r8, aFailedToAlloca_4; "Failed to allocate display name for %S"
0x140011700  mov     rcx, r15
0x140011703  call    WusaLogDebugEventA
0x140011708  mov     rcx, [rbp+pv]; pv
0x14001170c  test    rcx, rcx
0x14001170f  jz      short loc_14001171B
0x140011711  call    cs:__imp_CoTaskMemFree
0x140011717  mov     [rbp+pv], r14
0x14001171b  mov     rcx, [rbp+arg_0]; pv
0x14001171f  test    rcx, rcx
0x140011722  jz      short loc_14001172E
0x140011724  call    cs:__imp_CoTaskMemFree
0x14001172a  mov     [rbp+arg_0], r14
0x14001172e  mov     rcx, [rbp+String1]; pv
0x140011732  test    rcx, rcx
0x140011735  jz      short loc_140011741
0x140011737  call    cs:__imp_CoTaskMemFree
0x14001173d  mov     [rbp+String1], r14
0x140011741  mov     rcx, [rbp+hMem]; hMem
0x140011745  test    rcx, rcx
0x140011748  jz      short loc_140011754
0x14001174a  call    cs:__imp_LocalFree
0x140011750  mov     [rbp+hMem], r14
0x140011754  mov     rcx, [rbp+arg_10]; hMem
0x140011758  test    rcx, rcx
0x14001175b  jz      short loc_140011767
0x14001175d  call    cs:__imp_LocalFree
0x140011763  mov     [rbp+arg_10], r14
0x140011767  test    ebx, ebx
0x140011769  jns     short loc_1400117A8
0x14001176b  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x14001176f  mov     [rbp+var_8], r14
0x140011773  mov     ecx, ebx; dwMessageId
0x140011775  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14001177a  mov     rdi, [rbp+var_8]
0x14001177e  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140011785  mov     r9d, ebx
0x140011788  mov     [rsp+40h+var_20], rdi
0x14001178d  mov     edx, 1C7h
0x140011792  mov     rcx, r15
0x140011795  call    WusaLogDebugEventA
0x14001179a  test    rdi, rdi
0x14001179d  jz      short loc_1400117A8
0x14001179f  mov     rcx, rdi; hMem
0x1400117a2  call    cs:__imp_LocalFree
0x1400117a8  mov     eax, ebx
0x1400117aa  add     rsp, 40h
0x1400117ae  pop     r15
0x1400117b0  pop     r14
0x1400117b2  pop     r12
0x1400117b4  pop     rdi
0x1400117b5  pop     rsi
0x1400117b6  pop     rbx
0x1400117b7  pop     rbp
0x1400117b8  retn
```
