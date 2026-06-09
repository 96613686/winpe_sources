# std::unique_ptr<Diagnostics::TdhManifest,std::default_delete<Diagnostics::TdhManifest>>::~unique_ptr<Diagnostics::TdhManifest,std::default_delete<Diagnostics::TdhManifest>>(void)

- ea: `0x1800468c4`
- end: `0x18004693b`
- name: `??1?$unique_ptr@VTdhManifest@Diagnostics@@U?$default_delete@VTdhManifest@Diagnostics@@@std@@@std@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(const char **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18002fd64`
- `0x180051534`
- `0x1800544c8`
- `0x18005bfd4`
- `0x1800995fd`

## callees

- `0x180018eec`
- `0x1800468c4`
- `0x1800672fc`
- `0x18008ffd4`

## import_xrefs

- `tdh!TdhUnloadManifest` at `0x1800468eb`
- `tdh!TdhUnloadManifest` at `0x1800468eb`

## string_xrefs

- `0x1800468f6`: `TdhUnloadManifest failed for: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::unique_ptr<Diagnostics::TdhManifest>::~unique_ptr<Diagnostics::TdhManifest>(const char **a1)
{
  char *v1; // rbx
  const char *v2; // rdi
  WCHAR *v3; // rcx
  TDHSTATUS v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (char *)*a1;
  if ( *a1 )
  {
    v2 = *a1;
    if ( *((_QWORD *)v1 + 3) <= 7u )
    {
      v3 = (WCHAR *)*a1;
    }
    else
    {
      v2 = *(const char **)v1;
      v3 = *(WCHAR **)v1;
    }
    v4 = TdhUnloadManifest(v3);
    wil::details::in1diag3::Log_IfWin32ErrorMsg(
      retaddr,
      (void *)0x175,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\EtwFileProcessor.hpp",
      (const char *)v4,
      (unsigned int)"TdhUnloadManifest failed for: %ls",
      v2);
    std::wstring::~wstring((__int64)v1);
    operator delete(v1, 0x20u);
  }
}

```

## disassembly

```asm
0x1800468c4  mov     [rsp+arg_0], rbx
0x1800468c9  push    rdi
0x1800468ca  sub     rsp, 30h
0x1800468ce  mov     rbx, [rcx]
0x1800468d1  test    rbx, rbx
0x1800468d4  jz      short loc_180046930
0x1800468d6  cmp     qword ptr [rbx+18h], 7
0x1800468db  mov     rdi, rbx
0x1800468de  jbe     short loc_1800468E8
0x1800468e0  mov     rdi, [rbx]
0x1800468e3  mov     rcx, rdi
0x1800468e6  jmp     short loc_1800468EB
0x1800468e8  mov     rcx, rbx; Manifest
0x1800468eb  call    cs:__imp_TdhUnloadManifest
0x1800468f1  mov     rcx, [rsp+38h]; this
0x1800468f6  lea     rdx, aTdhunloadmanif; "TdhUnloadManifest failed for: %ls"
0x1800468fd  mov     [rsp+38h+var_10], rdi; char *
0x180046902  lea     r8, aCW1SSrcCalliop_5; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180046909  mov     qword ptr [rsp+38h+var_18], rdx; unsigned int
0x18004690e  mov     r9d, eax; char *
0x180046911  mov     edx, 175h; void *
0x180046916  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18004691b  mov     rcx, rbx
0x18004691e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046923  mov     edx, 20h ; ' '; unsigned __int64
0x180046928  mov     rcx, rbx; void *
0x18004692b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180046930  mov     rbx, [rsp+38h+arg_0]
0x180046935  add     rsp, 30h
0x180046939  pop     rdi
0x18004693a  retn
```
