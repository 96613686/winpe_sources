# UnBCL::File::SetCompressionState(UnBCL::String const *,ushort)

- ea: `0x18003c960`
- end: `0x18003cb14`
- name: `?SetCompressionState@File@UnBCL@@SAHPEBVString@2@G@Z`
- size: `436`
- prototype: `__int64 __fastcall(const struct UnBCL::String *, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180002f50`
- `0x180002f90`
- `0x180025720`
- `0x18003c960`
- `0x180048fb0`
- `0x180049500`
- `0x18004a440`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003cab7`
- `KERNEL32!CloseHandle` at `0x18003cab7`
- `KERNEL32!DeviceIoControl` at `0x18003caab`
- `KERNEL32!DeviceIoControl` at `0x18003caab`
- `KERNEL32!CreateFileW` at `0x18003ca4b`
- `KERNEL32!CreateFileW` at `0x18003ca4b`
- `KERNEL32!GetFileAttributesW` at `0x18003c9ff`
- `KERNEL32!GetFileAttributesW` at `0x18003c9ff`
- `KERNEL32!SetFileAttributesW` at `0x18003ca20`
- `KERNEL32!SetFileAttributesW` at `0x18003cac7`
- `KERNEL32!SetFileAttributesW` at `0x18003ca20`
- `KERNEL32!SetFileAttributesW` at `0x18003cac7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnBCL::File::SetCompressionState(const struct UnBCL::String *a1, __int16 a2)
{
  unsigned int v3; // r12d
  struct UnBCL::String *FullPath; // rax
  __int64 v5; // rax
  struct UnBCL::String *v6; // rax
  struct UnBCL::String *v7; // r14
  DWORD FileAttributesW; // eax
  DWORD v9; // edi
  int v10; // esi
  HANDLE FileW; // r15
  void (__fastcall ***v13)(_QWORD, __int64); // [rsp+48h] [rbp-50h] BYREF
  void **v14; // [rsp+50h] [rbp-48h] BYREF
  struct UnBCL::String *v15; // [rsp+58h] [rbp-40h]
  _QWORD v16[2]; // [rsp+60h] [rbp-38h] BYREF
  __int16 InBuffer; // [rsp+A0h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+18h] BYREF

  if ( !a1 || !**((_WORD **)a1 + 2) )
    return 0;
  v3 = 0;
  v14 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  v15 = 0;
  try
  {
    FullPath = UnBCL::Path::GetFullPath(a1);
    v5 = UnBCL::_::MakeSmartPtr<UnBCL::String>(v16, FullPath);
    v6 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v5 + 8), 1);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v14, v6);
    v16[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v16);
    v7 = v15;
    UnBCL::Path::CheckPathTooLong(v15);
  }
  catch ( UnBCL::Exception *v13 )
  {
    if ( v13 )
      (**v13)(v13, 1);
    v14 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v14);
    return 0;
  }
  FileAttributesW = GetFileAttributesW(*((LPCWSTR *)v7 + 2));
  v9 = FileAttributesW;
  if ( FileAttributesW != -1 )
  {
    v10 = FileAttributesW & 1;
    if ( (FileAttributesW & 1) != 0 )
      SetFileAttributesW(*((LPCWSTR *)v7 + 2), FileAttributesW & 0xFFFFFFFE);
    FileW = CreateFileW(*((LPCWSTR *)v7 + 2), 0xC0000000, 1u, 0, 3u, 0x82000080, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      InBuffer = a2;
      BytesReturned = 0;
      v3 = DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0);
      CloseHandle(FileW);
    }
    if ( v10 )
      SetFileAttributesW(*((LPCWSTR *)v7 + 2), v9);
  }
  v14 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v14);
  return v3;
}

```

## disassembly

```asm
0x18003c960  mov     r11, rsp
0x18003c963  push    rdi
0x18003c964  push    r12
0x18003c966  push    r13
0x18003c968  push    r14
0x18003c96a  push    r15
0x18003c96c  sub     rsp, 70h
0x18003c970  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x18003c978  mov     [r11+10h], rbx
0x18003c97c  mov     [r11+20h], rsi
0x18003c980  movzx   r13d, dx
0x18003c984  xor     r15d, r15d
0x18003c987  test    rcx, rcx
0x18003c98a  jz      loc_18003CAF8
0x18003c990  mov     rax, [rcx+10h]
0x18003c994  cmp     [rax], r15w
0x18003c998  jz      loc_18003CAF8
0x18003c99e  mov     r12d, r15d
0x18003c9a1  lea     rbx, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003c9a8  mov     [r11-48h], rbx
0x18003c9ac  mov     [r11-40h], r15
0x18003c9b0  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18003c9b5  mov     rdx, rax
0x18003c9b8  lea     rcx, [rsp+98h+var_38]
0x18003c9bd  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18003c9c2  nop
0x18003c9c3  lea     edx, [r15+1]; int
0x18003c9c7  mov     rcx, [rax+8]; struct UnBCL::String *
0x18003c9cb  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18003c9d0  mov     rdx, rax
0x18003c9d3  lea     rcx, [rsp+98h+var_48]
0x18003c9d8  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18003c9dd  nop
0x18003c9de  mov     [rsp+98h+var_38], rbx
0x18003c9e3  lea     rcx, [rsp+98h+var_38]
0x18003c9e8  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003c9ed  mov     r14, [rsp+98h+var_40]
0x18003c9f2  mov     rcx, r14; struct UnBCL::String *
0x18003c9f5  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18003c9fa  nop
0x18003c9fb  mov     rcx, [r14+10h]; lpFileName
0x18003c9ff  call    cs:__imp_GetFileAttributesW
0x18003ca05  mov     edi, eax
0x18003ca07  cmp     eax, 0FFFFFFFFh
0x18003ca0a  jz      loc_18003CACE
0x18003ca10  mov     esi, eax
0x18003ca12  and     esi, 1
0x18003ca15  jz      short loc_18003CA26
0x18003ca17  mov     edx, eax
0x18003ca19  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18003ca1c  mov     rcx, [r14+10h]; lpFileName
0x18003ca20  call    cs:__imp_SetFileAttributesW
0x18003ca26  mov     [rsp+98h+hTemplateFile], r15; hTemplateFile
0x18003ca2b  mov     [rsp+98h+dwFlagsAndAttributes], 82000080h; dwFlagsAndAttributes
0x18003ca33  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18003ca3b  xor     r9d, r9d; lpSecurityAttributes
0x18003ca3e  mov     edx, 0C0000000h; dwDesiredAccess
0x18003ca43  lea     r8d, [r9+1]; dwShareMode
0x18003ca47  mov     rcx, [r14+10h]; lpFileName
0x18003ca4b  call    cs:__imp_CreateFileW
0x18003ca51  mov     r15, rax
0x18003ca54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ca58  jz      short loc_18003CABD
0x18003ca5a  mov     [rsp+98h+InBuffer], r13w
0x18003ca63  mov     [rsp+98h+BytesReturned], 0
0x18003ca6e  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x18003ca77  lea     rax, [rsp+98h+BytesReturned]
0x18003ca7f  mov     [rsp+98h+hTemplateFile], rax; lpBytesReturned
0x18003ca84  mov     [rsp+98h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18003ca8c  mov     qword ptr [rsp+98h+dwCreationDisposition], 0; lpOutBuffer
0x18003ca95  mov     r9d, 2; nInBufferSize
0x18003ca9b  lea     r8, [rsp+98h+InBuffer]; lpInBuffer
0x18003caa3  mov     edx, 9C040h; dwIoControlCode
0x18003caa8  mov     rcx, r15; hDevice
0x18003caab  call    cs:__imp_DeviceIoControl
0x18003cab1  mov     r12d, eax
0x18003cab4  mov     rcx, r15; hObject
0x18003cab7  call    cs:__imp_CloseHandle
0x18003cabd  test    esi, esi
0x18003cabf  jz      short loc_18003CACE
0x18003cac1  mov     edx, edi; dwFileAttributes
0x18003cac3  mov     rcx, [r14+10h]; lpFileName
0x18003cac7  call    cs:__imp_SetFileAttributesW
0x18003cacd  nop
0x18003cace  mov     [rsp+98h+var_48], rbx
0x18003cad3  lea     rcx, [rsp+98h+var_48]
0x18003cad8  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003cadd  mov     eax, r12d
0x18003cae0  jmp     short loc_18003CAFA
0x18003cae2  lea     rbx, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18003cae9  mov     [rsp+98h+var_48], rbx
0x18003caee  lea     rcx, [rsp+98h+var_48]
0x18003caf3  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003caf8  xor     eax, eax
0x18003cafa  lea     r11, [rsp+98h+var_28]
0x18003caff  mov     rbx, [r11+38h]
0x18003cb03  mov     rsi, [r11+48h]
0x18003cb07  mov     rsp, r11
0x18003cb0a  pop     r15
0x18003cb0c  pop     r14
0x18003cb0e  pop     r13
0x18003cb10  pop     r12
0x18003cb12  pop     rdi
0x18003cb13  retn
```
