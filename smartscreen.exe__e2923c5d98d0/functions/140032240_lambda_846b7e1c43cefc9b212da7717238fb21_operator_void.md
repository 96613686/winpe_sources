# _lambda_846b7e1c43cefc9b212da7717238fb21_::operator()(void)

- ea: `0x140032240`
- end: `0x140032375`
- name: `??R_lambda_846b7e1c43cefc9b212da7717238fb21_@@QEBA?AV?$optional@G@std@@XZ`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x14001cb44`

## callees

- `0x14000c498`
- `0x140012780`
- `0x14001a1b8`
- `0x14001ca90`
- `0x140025aa0`
- `0x140032240`
- `0x1400360c0`
- `0x140062c80`

## import_xrefs

- `ntdll!NtCreateSection` at `0x1400322d3`
- `ntdll!NtCreateSection` at `0x1400322d3`
- `ntdll!NtQuerySection` at `0x140032315`
- `ntdll!NtQuerySection` at `0x140032315`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032297`

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
0x140032240  mov     [rsp-8+arg_10], rbx
0x140032245  push    rbp
0x140032246  push    rsi
0x140032247  push    rdi
0x140032248  lea     rbp, [rsp-47h]
0x14003224d  sub     rsp, 0B0h
0x140032254  mov     rax, cs:__security_cookie
0x14003225b  xor     rax, rsp
0x14003225e  mov     [rbp+57h+var_20], rax
0x140032262  mov     rbx, rdx
0x140032265  mov     [rbp+57h+hObject], 0
0x14003226d  mov     rdx, [rcx]
0x140032270  lea     rcx, [rbp+57h+var_78]
0x140032274  call    ?openFile@file_info@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBVpath@filesystem@std@@@Z; file_info::openFile(std::filesystem::path const &)
0x140032279  nop
0x14003227a  mov     rsi, [rax]
0x14003227d  mov     rdi, [rbp+57h+hObject]
0x140032281  lea     rax, [rdi-1]
0x140032285  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140032289  ja      short loc_1400322A6
0x14003228b  lea     rcx, [rbp+57h+var_80]; this
0x14003228f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140032294  mov     rcx, rdi; hObject
0x140032297  call    cs:__imp_CloseHandle
0x14003229d  lea     rcx, [rbp+57h+var_80]; this
0x1400322a1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400322a6  mov     [rbp+57h+hObject], 0
0x1400322ae  mov     [rsp+0C0h+FileHandle], rsi; FileHandle
0x1400322b3  mov     [rsp+0C0h+AllocationAttributes], 11000000h; AllocationAttributes
0x1400322bb  mov     [rsp+0C0h+SectionPageProtection], 2; int
0x1400322c3  xor     r9d, r9d; MaximumSize
0x1400322c6  xor     r8d, r8d; ObjectAttributes
0x1400322c9  lea     esi, [r9+1]
0x1400322cd  mov     edx, esi; DesiredAccess
0x1400322cf  lea     rcx, [rbp+57h+hObject]; SectionHandle
0x1400322d3  call    cs:__imp_NtCreateSection
0x1400322d9  mov     rcx, [rbp+5Fh]; this
0x1400322dd  test    eax, eax
0x1400322df  js      loc_140032367
0x1400322e5  lea     rcx, [rbp+57h+var_78]
0x1400322e9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400322ee  lea     edi, [rsi+3Fh]
0x1400322f1  mov     r8d, edi; Size
0x1400322f4  xor     edx, edx; Val
0x1400322f6  lea     rcx, [rbp+57h+SectionInformation]; void *
0x1400322fa  call    memset
0x1400322ff  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; int
0x140032308  mov     r9d, edi; Length
0x14003230b  lea     r8, [rbp+57h+SectionInformation]; SectionInformation
0x14003230f  mov     edx, esi; SectionInformationClass
0x140032311  mov     rcx, [rbp+57h+hObject]; SectionHandle
0x140032315  call    cs:__imp_NtQuerySection
0x14003231b  mov     rcx, [rbp+5Fh]; this
0x14003231f  test    eax, eax
0x140032321  js      short loc_140032359
0x140032323  movzx   ecx, [rbp+57h+var_30]
0x140032327  mov     [rbx], cx
0x14003232a  mov     [rbx+2], sil
0x14003232e  lea     rcx, [rbp+57h+hObject]
0x140032332  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140032337  mov     rax, rbx
0x14003233a  mov     rcx, [rbp+57h+var_20]
0x14003233e  xor     rcx, rsp; StackCookie
0x140032341  call    __security_check_cookie
0x140032346  mov     rbx, [rsp+0C0h+arg_10]
0x14003234e  add     rsp, 0B0h
0x140032355  pop     rdi
0x140032356  pop     rsi
0x140032357  pop     rbp
0x140032358  retn
0x140032359  mov     r9d, eax; char *
0x14003235c  mov     edx, 0FAh; void *
0x140032361  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140032367  mov     r9d, eax; char *
0x14003236a  mov     edx, 0F7h; void *
0x14003236f  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
