# UnBCL::Directory::IsDirectoryEmpty(UnBCL::String const *)

- ea: `0x18002e060`
- end: `0x18002e2b2`
- name: `?IsDirectoryEmpty@Directory@UnBCL@@SAHPEBVString@2@@Z`
- size: `594`
- prototype: `__int64 __fastcall(const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x180011570`
- `0x180025720`
- `0x18002e060`
- `0x1800477d0`
- `0x180049500`
- `0x18004a440`
- `0x18005b6d0`
- `0x18005b9f0`
- `0x18005bda0`
- `0x18005be50`
- `0x18005c060`
- `0x180064340`
- `0x180068fe6`
- `0x180069020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002e268`
- `KERNEL32!GetLastError` at `0x18002e268`
- `KERNEL32!FindFirstFileW` at `0x18002e1a3`
- `KERNEL32!FindFirstFileW` at `0x18002e1a3`
- `KERNEL32!FindNextFileW` at `0x18002e1e6`
- `KERNEL32!FindNextFileW` at `0x18002e1e6`
- `KERNEL32!FindClose` at `0x18002e1f7`
- `KERNEL32!FindClose` at `0x18002e1f7`

## string_xrefs

- `0x18002e28c`: `int __cdecl UnBCL::Directory::IsDirectoryEmpty(const class UnBCL::String *)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UnBCL::Directory::IsDirectoryEmpty(const struct UnBCL::String *a1)
{
  struct UnBCL::String *FullPath; // rax
  __int64 v2; // rax
  unsigned int v3; // edi
  struct UnBCL::String *v4; // rax
  UnBCL::String *v5; // rbx
  int v6; // eax
  const unsigned __int16 *v7; // rcx
  struct UnBCL::String *v8; // rax
  HANDLE FirstFileW; // rbx
  UnBCL::Win32Exception *v11; // rdi
  DWORD LastError; // ebx
  const struct UnBCL::String *v13; // rax
  __int64 v14; // rax
  _QWORD v15[2]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 pExceptionObject; // [rsp+48h] [rbp-C0h] BYREF
  void **v18; // [rsp+50h] [rbp-B8h] BYREF
  UnBCL::String *v19; // [rsp+58h] [rbp-B0h]
  _BYTE v20[16]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 *v21; // [rsp+70h] [rbp-98h]
  __int64 v22; // [rsp+78h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+88h] [rbp-80h] BYREF

  v22 = -2;
  FullPath = UnBCL::Path::GetFullPath(a1);
  v2 = UnBCL::_::MakeSmartPtr<UnBCL::String>(v15, FullPath);
  v3 = 1;
  v4 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v2 + 8), 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v18, v4);
  v15[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v15);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  UnBCL::String::String((UnBCL::String *)v20, 0x5Cu, 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v16, 0);
  v5 = v19;
  v6 = UnBCL::String::EndsWith(v19, v21, 1);
  v7 = (const unsigned __int16 *)*((_QWORD *)v5 + 2);
  if ( v6 )
    v8 = UnBCL::String::Concat(v7, L"*");
  else
    v8 = UnBCL::String::Concat(v7, v21, L"*");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v15, v8);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v16, v15[1]);
  v15[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v15);
  FirstFileW = FindFirstFileW(*(LPCWSTR *)(v16[1] + 16LL), &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v11 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v15[0] = v11;
    if ( v11 )
    {
      LastError = GetLastError();
      v13 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v16);
      v14 = UnBCL::Win32Exception::Win32Exception(v11, LastError, v13);
    }
    else
    {
      v14 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "int __cdecl UnBCL::Directory::IsDirectoryEmpty(const class UnBCL::String *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  while ( (FindFileData.dwFileAttributes & 0x10) != 0
       && FindFileData.cFileName[0] == 46
       && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
  {
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_13;
  }
  v3 = 0;
LABEL_13:
  FindClose(FirstFileW);
  v16[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v16);
  UnBCL::String::~String((UnBCL::String *)v20);
  v18 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v18);
  return v3;
}

```

## disassembly

```asm
0x18002e060  mov     rax, rsp
0x18002e063  push    rbp
0x18002e064  push    rdi
0x18002e065  push    r14
0x18002e067  lea     rbp, [rax-1F8h]
0x18002e06e  sub     rsp, 2E0h
0x18002e075  mov     [rsp+2F0h+var_280], 0FFFFFFFFFFFFFFFEh
0x18002e07e  mov     [rax+10h], rbx
0x18002e082  mov     [rax+18h], rsi
0x18002e086  mov     rax, cs:__security_cookie
0x18002e08d  xor     rax, rsp
0x18002e090  mov     [rbp+1F0h+var_20], rax
0x18002e097  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18002e09c  mov     rdx, rax
0x18002e09f  lea     rcx, [rsp+2F0h+var_2D0]
0x18002e0a4  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x18002e0a9  nop
0x18002e0aa  mov     edi, 1
0x18002e0af  mov     edx, edi; int
0x18002e0b1  mov     rcx, [rax+8]; struct UnBCL::String *
0x18002e0b5  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18002e0ba  mov     rdx, rax
0x18002e0bd  lea     rcx, [rsp+2F0h+var_2A8]
0x18002e0c2  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002e0c7  nop
0x18002e0c8  lea     r14, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002e0cf  mov     [rsp+2F0h+var_2D0], r14
0x18002e0d4  lea     rcx, [rsp+2F0h+var_2D0]
0x18002e0d9  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002e0de  xor     edx, edx; Val
0x18002e0e0  mov     r8d, 250h; Size
0x18002e0e6  lea     rcx, [rbp+1F0h+FindFileData]; void *
0x18002e0ea  call    memset_0
0x18002e0ef  lea     edx, [rdi+5Bh]; unsigned __int16
0x18002e0f2  mov     r8d, edi; int
0x18002e0f5  lea     rcx, [rsp+2F0h+var_298]; this
0x18002e0fa  call    ??0String@UnBCL@@QEAA@GH@Z; UnBCL::String::String(ushort,int)
0x18002e0ff  nop
0x18002e100  xor     edx, edx
0x18002e102  lea     rcx, [rsp+2F0h+var_2C0]
0x18002e107  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002e10c  nop
0x18002e10d  mov     rbx, [rsp+2F0h+var_2A0]
0x18002e112  mov     r8d, edi; int
0x18002e115  mov     rdx, [rsp+2F0h+var_288]; unsigned __int16 *
0x18002e11a  mov     rcx, rbx; this
0x18002e11d  call    ?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x18002e122  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18002e126  xor     esi, esi
0x18002e128  test    eax, eax
0x18002e12a  jz      short loc_18002E158
0x18002e12c  lea     rdx, asc_180080E7C; "*"
0x18002e133  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18002e138  mov     rdx, rax
0x18002e13b  lea     rcx, [rsp+2F0h+var_2D0]
0x18002e140  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002e145  nop
0x18002e146  mov     rdx, [rsp+2F0h+var_2C8]
0x18002e14b  lea     rcx, [rsp+2F0h+var_2C0]
0x18002e150  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002e155  nop
0x18002e156  jmp     short loc_18002E187
0x18002e158  lea     r8, asc_180080E7C; "*"
0x18002e15f  mov     rdx, [rsp+2F0h+var_288]; unsigned __int16 *
0x18002e164  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x18002e169  mov     rdx, rax
0x18002e16c  lea     rcx, [rsp+2F0h+var_2D0]
0x18002e171  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002e176  nop
0x18002e177  mov     rdx, [rsp+2F0h+var_2C8]
0x18002e17c  lea     rcx, [rsp+2F0h+var_2C0]
0x18002e181  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002e186  nop
0x18002e187  mov     [rsp+2F0h+var_2D0], r14
0x18002e18c  lea     rcx, [rsp+2F0h+var_2D0]
0x18002e191  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002e196  lea     rdx, [rbp+1F0h+FindFileData]; lpFindFileData
0x18002e19a  mov     rcx, [rsp+2F0h+var_2B8]
0x18002e19f  mov     rcx, [rcx+10h]; lpFileName
0x18002e1a3  call    cs:__imp_FindFirstFileW
0x18002e1a9  mov     rbx, rax
0x18002e1ac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e1b0  jz      loc_18002E251
0x18002e1b6  test    byte ptr [rbp+1F0h+FindFileData.dwFileAttributes], 10h
0x18002e1ba  jz      short loc_18002E1F2
0x18002e1bc  movzx   eax, [rbp+1F0h+FindFileData.cFileName+2]
0x18002e1c0  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x18002e1c5  jnz     short loc_18002E1F2
0x18002e1c7  test    ax, ax
0x18002e1ca  jz      short loc_18002E1DF
0x18002e1cc  cmp     [rbp+1F0h+FindFileData.cFileName], 2Eh ; '.'
0x18002e1d1  jnz     short loc_18002E1F2
0x18002e1d3  cmp     ax, 2Eh ; '.'
0x18002e1d7  jnz     short loc_18002E1F2
0x18002e1d9  cmp     [rbp+1F0h+FindFileData.cFileName+4], si
0x18002e1dd  jnz     short loc_18002E1F2
0x18002e1df  lea     rdx, [rbp+1F0h+FindFileData]; lpFindFileData
0x18002e1e3  mov     rcx, rbx; hFindFile
0x18002e1e6  call    cs:__imp_FindNextFileW
0x18002e1ec  test    eax, eax
0x18002e1ee  jnz     short loc_18002E1B6
0x18002e1f0  jmp     short loc_18002E1F4
0x18002e1f2  mov     edi, esi
0x18002e1f4  mov     rcx, rbx; hFindFile
0x18002e1f7  call    cs:__imp_FindClose
0x18002e1fd  nop
0x18002e1fe  mov     [rsp+2F0h+var_2C0], r14
0x18002e203  lea     rcx, [rsp+2F0h+var_2C0]
0x18002e208  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002e20d  nop
0x18002e20e  lea     rcx, [rsp+2F0h+var_298]; this
0x18002e213  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18002e218  nop
0x18002e219  mov     [rsp+2F0h+var_2A8], r14
0x18002e21e  lea     rcx, [rsp+2F0h+var_2A8]
0x18002e223  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002e228  mov     eax, edi
0x18002e22a  mov     rcx, [rbp+1F0h+var_20]
0x18002e231  xor     rcx, rsp; StackCookie
0x18002e234  call    __security_check_cookie
0x18002e239  lea     r11, [rsp+2F0h+var_10]
0x18002e241  mov     rbx, [r11+28h]
0x18002e245  mov     rsi, [r11+30h]
0x18002e249  mov     rsp, r11
0x18002e24c  pop     r14
0x18002e24e  pop     rdi
0x18002e24f  pop     rbp
0x18002e250  retn
0x18002e251  mov     ecx, 40h ; '@'; unsigned __int64
0x18002e256  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002e25b  mov     rdi, rax
0x18002e25e  mov     [rsp+2F0h+var_2D0], rax
0x18002e263  test    rax, rax
0x18002e266  jz      short loc_18002E289
0x18002e268  call    cs:__imp_GetLastError
0x18002e26e  mov     ebx, eax
0x18002e270  lea     rcx, [rsp+2F0h+var_2C0]
0x18002e275  call    ??C?$SmartPtr@VDecoder@UnBCL@@@UnBCL@@QEBAPEAVDecoder@1@XZ; UnBCL::SmartPtr<UnBCL::Decoder>::operator->(void)
0x18002e27a  mov     r8, rax; struct UnBCL::String *
0x18002e27d  mov     edx, ebx; dwMessageId
0x18002e27f  mov     rcx, rdi; this
0x18002e282  call    ??0Win32Exception@UnBCL@@QEAA@KPEBVString@1@@Z; UnBCL::Win32Exception::Win32Exception(ulong,UnBCL::String const *)
0x18002e287  jmp     short loc_18002E28C
0x18002e289  mov     rax, rsi
0x18002e28c  lea     rdx, aIntCdeclUnbclD; "int __cdecl UnBCL::Directory::IsDirecto"...
0x18002e293  mov     rcx, rax
0x18002e296  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002e29b  mov     [rsp+2F0h+pExceptionObject], rax
0x18002e2a0  lea     rdx, _TI6PEAVWin32Exception@UnBCL@@; pThrowInfo
0x18002e2a7  lea     rcx, [rsp+2F0h+pExceptionObject]; pExceptionObject
0x18002e2ac  call    _CxxThrowException_0
```
