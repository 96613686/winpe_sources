# _CopyCurrentHistoryItemToStream(IStream *)

- ea: `0x1800cda1c`
- end: `0x1800cdbe9`
- name: `?_CopyCurrentHistoryItemToStream@@YAJPEAUIStream@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(struct IStream *pstmTo)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cc210`

## callees

- `0x18000da00`
- `0x180013f14`
- `0x1800343ec`
- `0x180054130`
- `0x1800cda1c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cda84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cda84`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x1800cdba8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x1800cdba8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800cdb89`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800cdb89`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800cdb16`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800cdb16`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _CopyCurrentHistoryItemToStream(struct IStream *pstmTo)
{
  int ValueW; // ebx
  bool v3; // sf
  void *v4; // rdi
  __int64 (__fastcall *v5)(void *, _QWORD, const GUID *, GUID *, DWORD *); // rbx
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp-B0h] BYREF
  _WORD pvData[20]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszItem[264]; // [rsp+80h] [rbp-80h] BYREF

  pcbData[0] = 40;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
             L"SourceId",
             2u,
             0,
             pvData,
             pcbData);
  if ( !ValueW )
    goto LABEL_4;
  pvData[0] = 0;
  v3 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_4:
    v3 = ValueW < 0;
  }
  if ( !v3 )
  {
    ValueW = StringCchPrintfW(pszItem, 0x104u, L"%s%s", pvData, L".accountpicture-ms");
    if ( ValueW >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      ValueW = SHCreateItemInKnownFolder(
                 &FOLDERID_AccountPictures,
                 0x1000u,
                 pszItem,
                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                 &ppv);
      if ( ValueW >= 0 )
      {
        *(_QWORD *)pcbData = 0;
        v4 = ppv;
        v5 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, DWORD *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
        ValueW = v5(v4, 0, &BHID_SFObject, &GUID_0000000c_0000_0000_c000_000000000046, pcbData);
        if ( ValueW >= 0 )
        {
          pui.QuadPart = 0;
          ValueW = IStream_Size(*(IStream **)pcbData, &pui);
          if ( ValueW >= 0 )
            ValueW = IStream_Copy(*(IStream **)pcbData, pstmTo, pui.LowPart);
        }
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800cda1c  push    rbp
0x1800cda1e  push    rbx
0x1800cda1f  push    rsi
0x1800cda20  push    rdi
0x1800cda21  lea     rbp, [rsp-1A8h]
0x1800cda29  sub     rsp, 2A8h
0x1800cda30  mov     rax, cs:__security_cookie
0x1800cda37  xor     rax, rsp
0x1800cda3a  mov     [rbp+1C0h+var_30], rax
0x1800cda41  mov     rsi, rcx
0x1800cda44  mov     [rsp+2C0h+var_280], 28h ; '('
0x1800cda4c  lea     rax, [rsp+2C0h+var_280]
0x1800cda51  mov     [rsp+2C0h+pcbData], rax; pcbData
0x1800cda56  lea     rax, [rsp+2C0h+var_268]
0x1800cda5b  mov     [rsp+2C0h+pvData], rax; pvData
0x1800cda60  mov     [rsp+2C0h+pdwType], 0; pdwType
0x1800cda69  mov     r9d, 2; dwFlags
0x1800cda6f  lea     r8, aSourceid; "SourceId"
0x1800cda76  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800cda7d  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800cda84  call    cs:__imp_RegGetValueW
0x1800cda8b  nop     dword ptr [rax+rax+00h]
0x1800cda90  mov     ebx, eax
0x1800cda92  test    eax, eax
0x1800cda94  jz      short loc_1800CDAAA
0x1800cda96  xor     eax, eax
0x1800cda98  mov     [rsp+2C0h+var_268], ax
0x1800cda9d  test    ebx, ebx
0x1800cda9f  jle     short loc_1800CDAAC
0x1800cdaa1  movzx   ebx, bx
0x1800cdaa4  or      ebx, 80070000h
0x1800cdaaa  test    ebx, ebx
0x1800cdaac  js      loc_1800CDBCB
0x1800cdab2  lea     rax, aAccountpicture; ".accountpicture-ms"
0x1800cdab9  mov     [rsp+2C0h+pdwType], rax
0x1800cdabe  lea     r9, [rsp+2C0h+var_268]
0x1800cdac3  lea     r8, aSS_2; "%s%s"
0x1800cdaca  mov     edx, 104h; unsigned __int64
0x1800cdacf  lea     rcx, [rbp+1C0h+pszItem]; unsigned __int16 *
0x1800cdad3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cdad8  mov     ebx, eax
0x1800cdada  test    eax, eax
0x1800cdadc  js      loc_1800CDBCB
0x1800cdae2  mov     [rsp+2C0h+ppv], 0
0x1800cdaeb  lea     rcx, [rsp+2C0h+ppv]
0x1800cdaf0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdaf5  lea     rax, [rsp+2C0h+ppv]
0x1800cdafa  mov     [rsp+2C0h+pdwType], rax; ppv
0x1800cdaff  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800cdb06  lea     r8, [rbp+1C0h+pszItem]; pszItem
0x1800cdb0a  mov     edx, 1000h; dwKFFlags
0x1800cdb0f  lea     rcx, FOLDERID_AccountPictures; kfid
0x1800cdb16  call    cs:__imp_SHCreateItemInKnownFolder
0x1800cdb1d  nop     dword ptr [rax+rax+00h]
0x1800cdb22  mov     ebx, eax
0x1800cdb24  test    eax, eax
0x1800cdb26  js      loc_1800CDBC1
0x1800cdb2c  mov     qword ptr [rsp+2C0h+var_280], 0
0x1800cdb35  mov     rdi, [rsp+2C0h+ppv]
0x1800cdb3a  mov     rax, [rdi]
0x1800cdb3d  mov     rbx, [rax+18h]
0x1800cdb41  lea     rcx, [rsp+2C0h+var_280]
0x1800cdb46  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800cdb4b  lea     rax, [rsp+2C0h+var_280]
0x1800cdb50  mov     [rsp+2C0h+pdwType], rax
0x1800cdb55  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x1800cdb5c  lea     r8, BHID_SFObject
0x1800cdb63  xor     edx, edx
0x1800cdb65  mov     rcx, rdi
0x1800cdb68  mov     rax, rbx
0x1800cdb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdb70  mov     ebx, eax
0x1800cdb72  test    eax, eax
0x1800cdb74  js      short loc_1800CDBB6
0x1800cdb76  mov     qword ptr [rsp+2C0h+pui], 0
0x1800cdb7f  lea     rdx, [rsp+2C0h+pui]; pui
0x1800cdb84  mov     rcx, qword ptr [rsp+2C0h+var_280]; pstm
0x1800cdb89  call    cs:__imp_IStream_Size
0x1800cdb90  nop     dword ptr [rax+rax+00h]
0x1800cdb95  mov     ebx, eax
0x1800cdb97  test    eax, eax
0x1800cdb99  js      short loc_1800CDBB6
0x1800cdb9b  mov     r8d, dword ptr [rsp+2C0h+pui]; cb
0x1800cdba0  mov     rdx, rsi; pstmTo
0x1800cdba3  mov     rcx, qword ptr [rsp+2C0h+var_280]; pstmFrom
0x1800cdba8  call    cs:__imp_IStream_Copy
0x1800cdbaf  nop     dword ptr [rax+rax+00h]
0x1800cdbb4  mov     ebx, eax
0x1800cdbb6  lea     rcx, [rsp+2C0h+var_280]
0x1800cdbbb  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800cdbc0  nop
0x1800cdbc1  lea     rcx, [rsp+2C0h+ppv]
0x1800cdbc6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdbcb  mov     eax, ebx
0x1800cdbcd  mov     rcx, [rbp+1C0h+var_30]
0x1800cdbd4  xor     rcx, rsp; StackCookie
0x1800cdbd7  call    __security_check_cookie
0x1800cdbdc  add     rsp, 2A8h
0x1800cdbe3  pop     rdi
0x1800cdbe4  pop     rsi
0x1800cdbe5  pop     rbx
0x1800cdbe6  pop     rbp
0x1800cdbe7  retn
```
