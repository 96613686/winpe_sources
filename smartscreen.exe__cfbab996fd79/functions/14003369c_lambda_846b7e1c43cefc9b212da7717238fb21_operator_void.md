# _lambda_846b7e1c43cefc9b212da7717238fb21_::operator()(void)

- ea: `0x14003369c`
- end: `0x1400337e4`
- name: `??R_lambda_846b7e1c43cefc9b212da7717238fb21_@@QEBA?AV?$optional@G@std@@XZ`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x14001dab4`

## callees

- `0x14000cb90`
- `0x14001317c`
- `0x14001afa0`
- `0x14001d9f4`
- `0x140026c20`
- `0x14003369c`
- `0x1400375d0`
- `0x140064940`

## import_xrefs

- `ntdll!NtCreateSection` at `0x140033735`
- `ntdll!NtCreateSection` at `0x140033735`
- `ntdll!NtQuerySection` at `0x14003377d`
- `ntdll!NtQuerySection` at `0x14003377d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400336f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400336f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_846b7e1c43cefc9b212da7717238fb21_::operator()(_QWORD **a1, __int64 a2)
{
  char *FileHandle; // rsi
  HANDLE v4; // rdi
  NTSTATUS Section; // eax
  unsigned int v6; // r8d
  NTSTATUS v7; // eax
  unsigned int v8; // r8d
  int SectionPageProtection; // [rsp+20h] [rbp-49h]
  int SectionPageProtectiona; // [rsp+20h] [rbp-49h]
  _BYTE v12[8]; // [rsp+40h] [rbp-29h] BYREF
  const char *v13; // [rsp+48h] [rbp-21h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-19h] BYREF
  _WORD SectionInformation[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  hObject[0] = 0;
  FileHandle = (char *)*file_info::openFile(&v13, *a1);
  v4 = hObject[0];
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v12);
    CloseHandle(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
  }
  hObject[0] = 0;
  Section = NtCreateSection(hObject, 1u, 0, 0, 2u, 0x11000000u, FileHandle);
  if ( Section < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xF7,
      v6,
      (const char *)(unsigned int)Section,
      SectionPageProtection);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
  memset(SectionInformation, 0, sizeof(SectionInformation));
  v7 = NtQuerySection(hObject[0], SectionImageInformation, SectionInformation, 0x40u, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xFA,
      v8,
      (const char *)(unsigned int)v7,
      SectionPageProtectiona);
  *(_WORD *)a2 = SectionInformation[24];
  *(_BYTE *)(a2 + 2) = 1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hObject);
  return a2;
}

```

## disassembly

```asm
0x14003369c  mov     [rsp-8+arg_10], rbx
0x1400336a1  push    rbp
0x1400336a2  push    rsi
0x1400336a3  push    rdi
0x1400336a4  lea     rbp, [rsp-47h]
0x1400336a9  sub     rsp, 0B0h
0x1400336b0  mov     rax, cs:__security_cookie
0x1400336b7  xor     rax, rsp
0x1400336ba  mov     [rbp+57h+var_20], rax
0x1400336be  mov     rbx, rdx
0x1400336c1  mov     [rbp+57h+hObject], 0
0x1400336c9  mov     rdx, [rcx]
0x1400336cc  lea     rcx, [rbp+57h+var_78]
0x1400336d0  call    ?openFile@file_info@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBVpath@filesystem@std@@@Z; file_info::openFile(std::filesystem::path const &)
0x1400336d5  nop
0x1400336d6  mov     rsi, [rax]
0x1400336d9  mov     rdi, [rbp+57h+hObject]
0x1400336dd  lea     rax, [rdi-1]
0x1400336e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400336e5  ja      short loc_140033708
0x1400336e7  lea     rcx, [rbp+57h+var_80]; this
0x1400336eb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400336f0  mov     rcx, rdi; hObject
0x1400336f3  call    cs:__imp_CloseHandle
0x1400336fa  nop     dword ptr [rax+rax+00h]
0x1400336ff  lea     rcx, [rbp+57h+var_80]; this
0x140033703  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140033708  mov     [rbp+57h+hObject], 0
0x140033710  mov     [rsp+0C0h+FileHandle], rsi; FileHandle
0x140033715  mov     [rsp+0C0h+AllocationAttributes], 11000000h; AllocationAttributes
0x14003371d  mov     [rsp+0C0h+SectionPageProtection], 2; int
0x140033725  xor     r9d, r9d; MaximumSize
0x140033728  xor     r8d, r8d; ObjectAttributes
0x14003372b  lea     esi, [r9+1]
0x14003372f  mov     edx, esi; DesiredAccess
0x140033731  lea     rcx, [rbp+57h+hObject]; SectionHandle
0x140033735  call    cs:__imp_NtCreateSection
0x14003373c  nop     dword ptr [rax+rax+00h]
0x140033741  mov     rcx, [rbp+5Fh]; this
0x140033745  test    eax, eax
0x140033747  js      loc_1400337D6
0x14003374d  lea     rcx, [rbp+57h+var_78]
0x140033751  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140033756  lea     edi, [rsi+3Fh]
0x140033759  mov     r8d, edi; Size
0x14003375c  xor     edx, edx; Val
0x14003375e  lea     rcx, [rbp+57h+SectionInformation]; void *
0x140033762  call    memset
0x140033767  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; int
0x140033770  mov     r9d, edi; Length
0x140033773  lea     r8, [rbp+57h+SectionInformation]; SectionInformation
0x140033777  mov     edx, esi; SectionInformationClass
0x140033779  mov     rcx, [rbp+57h+hObject]; SectionHandle
0x14003377d  call    cs:__imp_NtQuerySection
0x140033784  nop     dword ptr [rax+rax+00h]
0x140033789  mov     rcx, [rbp+5Fh]; this
0x14003378d  test    eax, eax
0x14003378f  js      short loc_1400337C8
0x140033791  movzx   ecx, [rbp+57h+var_30]
0x140033795  mov     [rbx], cx
0x140033798  mov     [rbx+2], sil
0x14003379c  lea     rcx, [rbp+57h+hObject]
0x1400337a0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400337a5  mov     rax, rbx
0x1400337a8  mov     rcx, [rbp+57h+var_20]
0x1400337ac  xor     rcx, rsp; StackCookie
0x1400337af  call    __security_check_cookie
0x1400337b4  mov     rbx, [rsp+0C0h+arg_10]
0x1400337bc  add     rsp, 0B0h
0x1400337c3  pop     rdi
0x1400337c4  pop     rsi
0x1400337c5  pop     rbp
0x1400337c6  retn
0x1400337c8  mov     r9d, eax; char *
0x1400337cb  mov     edx, 0FAh; void *
0x1400337d0  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400337d6  mov     r9d, eax; char *
0x1400337d9  mov     edx, 0F7h; void *
0x1400337de  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
