# CProfileNotificationHandler::OnCreate(ushort const *,ushort const *,ulong)

- ea: `0x180006730`
- end: `0x180006884`
- name: `?OnCreate@CProfileNotificationHandler@@UEAAJPEBG0K@Z`
- size: `340`
- prototype: `__int64 __fastcall(CProfileNotificationHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002230`
- `0x180002b8e`
- `0x180005968`
- `0x180006730`
- `0x180007594`
- `0x18000834c`
- `0x1800092e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000684d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000684d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000676f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000676f`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x180006800`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x180006800`

## pseudocode

```c
__int64 __fastcall CProfileNotificationHandler::OnCreate(
        CProfileNotificationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int LastError; // eax
  signed int v5; // ebx
  HKEY v6; // rcx
  const unsigned __int16 *v7; // r8
  unsigned int v8; // r9d
  unsigned int v10; // [rsp+28h] [rbp-D8h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  PSID Sid; // [rsp+40h] [rbp-C0h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v15[264]; // [rsp+A0h] [rbp-60h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    pv = 0;
    v5 = SHTranslateSIDToName(Sid, &pv);
    if ( v5 >= 0 )
    {
      hObject = 0;
      v5 = SHCreateDataFileForUser(pv, a2, &hObject);
      if ( v5 >= 0 )
      {
        CloseHandle(hObject);
        memset_0(&spc, 0, sizeof(spc));
        if ( GetPwrCapabilities(&spc) )
        {
          if ( spc.spare2[2] && (int)StringCchPrintfW(v15, 0x104u, L"%s\\Control Panel\\Desktop", a2) >= 0 )
          {
            LODWORD(hObject) = 900;
            _RegSetKeyValue(v6, v15, v7, v8, (BYTE *)&hObject, v10);
          }
        }
      }
      CoTaskMemFree(pv);
    }
    LocalFree(Sid);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006730  mov     [rsp-8+arg_0], rbx
0x180006735  mov     [rsp-8+arg_10], rdi
0x18000673a  push    rbp
0x18000673b  lea     rbp, [rsp-1C0h]
0x180006743  sub     rsp, 2C0h
0x18000674a  mov     rax, cs:__security_cookie
0x180006751  xor     rax, rsp
0x180006754  mov     [rbp+1C0h+var_10], rax
0x18000675b  mov     rdi, rdx
0x18000675e  mov     [rsp+2C0h+Sid], 0
0x180006767  mov     rcx, rdi; StringSid
0x18000676a  lea     rdx, [rsp+2C0h+Sid]; Sid
0x18000676f  call    cs:__imp_ConvertStringSidToSidW
0x180006775  test    eax, eax
0x180006777  jnz     short loc_18000679D
0x180006779  call    cs:__imp_GetLastError
0x18000677f  mov     ebx, eax
0x180006781  test    eax, eax
0x180006783  jle     short loc_18000678E
0x180006785  movzx   ebx, ax
0x180006788  or      ebx, 80070000h
0x18000678e  test    ebx, ebx
0x180006790  mov     eax, 80004005h
0x180006795  cmovns  ebx, eax
0x180006798  jmp     loc_18000685E
0x18000679d  mov     rcx, [rsp+2C0h+Sid]
0x1800067a2  lea     rdx, [rsp+2C0h+pv]
0x1800067a7  mov     [rsp+2C0h+pv], 0
0x1800067b0  call    SHTranslateSIDToName
0x1800067b5  mov     ebx, eax
0x1800067b7  test    eax, eax
0x1800067b9  js      loc_180006853
0x1800067bf  mov     rcx, [rsp+2C0h+pv]
0x1800067c4  lea     r8, [rsp+2C0h+hObject]
0x1800067c9  mov     rdx, rdi
0x1800067cc  mov     [rsp+2C0h+hObject], 0
0x1800067d5  call    SHCreateDataFileForUser
0x1800067da  mov     ebx, eax
0x1800067dc  test    eax, eax
0x1800067de  js      short loc_180006848
0x1800067e0  mov     rcx, [rsp+2C0h+hObject]; hObject
0x1800067e5  call    cs:__imp_CloseHandle
0x1800067eb  xor     edx, edx; Val
0x1800067ed  lea     rcx, [rsp+2C0h+spc]; void *
0x1800067f2  lea     r8d, [rdx+4Ch]; Size
0x1800067f6  call    memset_0
0x1800067fb  lea     rcx, [rsp+2C0h+spc]; lpspc
0x180006800  call    cs:__imp_GetPwrCapabilities
0x180006806  test    al, al
0x180006808  jz      short loc_180006848
0x18000680a  cmp     [rsp+2C0h+spc.spare2+2], 0
0x18000680f  jz      short loc_180006848
0x180006811  mov     r9, rdi
0x180006814  lea     r8, aSControlPanelD; "%s\\Control Panel\\Desktop"
0x18000681b  mov     edx, 104h; unsigned __int64
0x180006820  lea     rcx, [rbp+1C0h+var_220]; unsigned __int16 *
0x180006824  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006829  test    eax, eax
0x18000682b  js      short loc_180006848
0x18000682d  lea     rax, [rsp+2C0h+hObject]
0x180006832  mov     dword ptr [rsp+2C0h+hObject], 384h
0x18000683a  lea     rdx, [rbp+1C0h+var_220]; unsigned __int16 *
0x18000683e  mov     [rsp+2C0h+lpData], rax; lpData
0x180006843  call    ?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z; _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180006848  mov     rcx, [rsp+2C0h+pv]; pv
0x18000684d  call    cs:__imp_CoTaskMemFree
0x180006853  mov     rcx, [rsp+2C0h+Sid]; hMem
0x180006858  call    cs:__imp_LocalFree
0x18000685e  mov     eax, ebx
0x180006860  mov     rcx, [rbp+1C0h+var_10]
0x180006867  xor     rcx, rsp; StackCookie
0x18000686a  call    __security_check_cookie
0x18000686f  lea     r11, [rsp+2C0h+var_s0]
0x180006877  mov     rbx, [r11+10h]
0x18000687b  mov     rdi, [r11+20h]
0x18000687f  mov     rsp, r11
0x180006882  pop     rbp
0x180006883  retn
```
