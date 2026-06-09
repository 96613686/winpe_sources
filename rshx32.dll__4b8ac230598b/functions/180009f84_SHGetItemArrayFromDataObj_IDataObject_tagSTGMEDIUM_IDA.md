# SHGetItemArrayFromDataObj(IDataObject *,tagSTGMEDIUM *,_IDA * *)

- ea: `0x180009f84`
- end: `0x18000a0dc`
- name: `?SHGetItemArrayFromDataObj@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct IDataObject *, struct tagSTGMEDIUM *, struct _IDA **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d90`

## callees

- `0x180009f84`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0ab`
- `KERNEL32!GlobalLock` at `0x18000a094`
- `KERNEL32!GlobalLock` at `0x18000a094`
- `USER32!RegisterClipboardFormatW` at `0x180009fb2`
- `USER32!RegisterClipboardFormatW` at `0x180009fbf`
- `USER32!RegisterClipboardFormatW` at `0x180009fd3`
- `USER32!RegisterClipboardFormatW` at `0x180009fe0`
- `USER32!RegisterClipboardFormatW` at `0x180009fed`
- `USER32!RegisterClipboardFormatW` at `0x180009ffa`
- `USER32!RegisterClipboardFormatW` at `0x18000a007`
- `USER32!RegisterClipboardFormatW` at `0x18000a01b`
- `USER32!RegisterClipboardFormatW` at `0x18000a028`
- `USER32!RegisterClipboardFormatW` at `0x180009fb2`
- `USER32!RegisterClipboardFormatW` at `0x180009fbf`
- `USER32!RegisterClipboardFormatW` at `0x180009fd3`
- `USER32!RegisterClipboardFormatW` at `0x180009fe0`
- `USER32!RegisterClipboardFormatW` at `0x180009fed`
- `USER32!RegisterClipboardFormatW` at `0x180009ffa`
- `USER32!RegisterClipboardFormatW` at `0x18000a007`
- `USER32!RegisterClipboardFormatW` at `0x18000a01b`
- `USER32!RegisterClipboardFormatW` at `0x18000a028`
- `ole32!ReleaseStgMedium` at `0x18000a0a5`
- `ole32!ReleaseStgMedium` at `0x18000a0a5`

## string_xrefs

- `0x180009fc5`: `FileGroupDescriptor`
- `0x180009fd9`: `FileGroupDescriptorW`

## pseudocode

```c
__int64 __fastcall SHGetItemArrayFromDataObj(struct IDataObject *a1, struct tagSTGMEDIUM *a2, struct _IDA **a3)
{
  signed int v6; // ebx
  struct _IDA *v7; // rax
  signed int LastError; // eax
  unsigned __int16 v10; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+22h] [rbp-26h]
  __int16 v12; // [rsp+26h] [rbp-22h]
  __int64 v13; // [rsp+28h] [rbp-20h]
  int v14; // [rsp+30h] [rbp-18h]
  int v15; // [rsp+34h] [rbp-14h]
  __int64 v16; // [rsp+38h] [rbp-10h]

  if ( !g_cfAsyncFlag_Storage )
  {
    RegisterClipboardFormatW(L"UniformResourceLocator");
    g_cfHIDA_Storage = RegisterClipboardFormatW(L"Shell IDList Array");
    RegisterClipboardFormatW(L"FileGroupDescriptor");
    RegisterClipboardFormatW(L"FileGroupDescriptorW");
    RegisterClipboardFormatW(L"Shell Object Offsets");
    RegisterClipboardFormatW(L"EnterpriseDataProtectionId");
    g_cfAsyncFlag_Storage = RegisterClipboardFormatW(L"AsyncFlag");
    RegisterClipboardFormatW(L"FilePropertyStore");
    RegisterClipboardFormatW(L"FilePropertyStoreByteSize");
  }
  *a3 = 0;
  v15 = -1;
  *(_OWORD *)&a2->tymed = 0;
  a2->pUnkForRelease = 0;
  v10 = g_cfHIDA_Storage;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 1;
  v16 = 1;
  v6 = ((__int64 (__fastcall *)(struct IDataObject *, unsigned __int16 *, struct tagSTGMEDIUM *))a1->lpVtbl->GetData)(
         a1,
         &v10,
         a2);
  if ( v6 >= 0 )
  {
    v7 = (struct _IDA *)GlobalLock(a2->hBitmap);
    *a3 = v7;
    if ( !v7 )
    {
      ReleaseStgMedium(a2);
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009f84  mov     [rsp+arg_0], rbx
0x180009f89  mov     [rsp+arg_8], rsi
0x180009f8e  push    rdi
0x180009f8f  sub     rsp, 40h
0x180009f93  xor     eax, eax
0x180009f95  mov     rsi, r8
0x180009f98  cmp     ax, cs:?g_cfAsyncFlag_Storage@@3GA; ushort g_cfAsyncFlag_Storage
0x180009f9f  mov     rdi, rdx
0x180009fa2  mov     rbx, rcx
0x180009fa5  jnz     loc_18000A02E
0x180009fab  lea     rcx, szFormat; "UniformResourceLocator"
0x180009fb2  call    cs:__imp_RegisterClipboardFormatW
0x180009fb8  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x180009fbf  call    cs:__imp_RegisterClipboardFormatW
0x180009fc5  lea     rcx, aFilegroupdescr_0; "FileGroupDescriptor"
0x180009fcc  mov     cs:?g_cfHIDA_Storage@@3GA, ax; ushort g_cfHIDA_Storage
0x180009fd3  call    cs:__imp_RegisterClipboardFormatW
0x180009fd9  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x180009fe0  call    cs:__imp_RegisterClipboardFormatW
0x180009fe6  lea     rcx, aShellObjectOff; "Shell Object Offsets"
0x180009fed  call    cs:__imp_RegisterClipboardFormatW
0x180009ff3  lea     rcx, aEnterprisedata; "EnterpriseDataProtectionId"
0x180009ffa  call    cs:__imp_RegisterClipboardFormatW
0x18000a000  lea     rcx, aAsyncflag; "AsyncFlag"
0x18000a007  call    cs:__imp_RegisterClipboardFormatW
0x18000a00d  lea     rcx, aFilepropertyst; "FilePropertyStore"
0x18000a014  mov     cs:?g_cfAsyncFlag_Storage@@3GA, ax; ushort g_cfAsyncFlag_Storage
0x18000a01b  call    cs:__imp_RegisterClipboardFormatW
0x18000a021  lea     rcx, aFilepropertyst_0; "FilePropertyStoreByteSize"
0x18000a028  call    cs:__imp_RegisterClipboardFormatW
0x18000a02e  xor     eax, eax
0x18000a030  mov     qword ptr [rsi], 0
0x18000a037  xorps   xmm0, xmm0
0x18000a03a  mov     [rsp+48h+var_14], 0FFFFFFFFh
0x18000a042  movups  xmmword ptr [rdi], xmm0
0x18000a045  mov     [rdi+10h], rax
0x18000a049  lea     rdx, [rsp+48h+var_28]
0x18000a04e  movzx   eax, cs:?g_cfHIDA_Storage@@3GA; ushort g_cfHIDA_Storage
0x18000a055  mov     r8, rdi
0x18000a058  mov     [rsp+48h+var_28], ax
0x18000a05d  mov     rcx, rbx
0x18000a060  xor     eax, eax
0x18000a062  mov     [rsp+48h+var_26], eax
0x18000a066  mov     [rsp+48h+var_22], ax
0x18000a06b  mov     [rsp+48h+var_20], rax
0x18000a070  mov     eax, 1
0x18000a075  mov     [rsp+48h+var_18], eax
0x18000a079  mov     [rsp+48h+var_10], rax
0x18000a07e  mov     rax, [rbx]
0x18000a081  mov     rax, [rax+18h]
0x18000a085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a08a  mov     ebx, eax
0x18000a08c  test    eax, eax
0x18000a08e  js      short loc_18000A0CA
0x18000a090  mov     rcx, [rdi+8]; hMem
0x18000a094  call    cs:__imp_GlobalLock
0x18000a09a  mov     [rsi], rax
0x18000a09d  test    rax, rax
0x18000a0a0  jnz     short loc_18000A0CA
0x18000a0a2  mov     rcx, rdi; LPSTGMEDIUM
0x18000a0a5  call    cs:__imp_ReleaseStgMedium
0x18000a0ab  call    cs:__imp_GetLastError
0x18000a0b1  mov     ebx, eax
0x18000a0b3  test    eax, eax
0x18000a0b5  jle     short loc_18000A0C0
0x18000a0b7  movzx   ebx, ax
0x18000a0ba  or      ebx, 80070000h
0x18000a0c0  test    ebx, ebx
0x18000a0c2  mov     eax, 80004005h
0x18000a0c7  cmovns  ebx, eax
0x18000a0ca  mov     rsi, [rsp+48h+arg_8]
0x18000a0cf  mov     eax, ebx
0x18000a0d1  mov     rbx, [rsp+48h+arg_0]
0x18000a0d6  add     rsp, 40h
0x18000a0da  pop     rdi
0x18000a0db  retn
```
