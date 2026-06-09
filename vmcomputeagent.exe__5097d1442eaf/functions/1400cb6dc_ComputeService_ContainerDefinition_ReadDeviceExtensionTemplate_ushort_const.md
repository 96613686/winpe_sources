# ComputeService::ContainerDefinition::ReadDeviceExtensionTemplate(ushort const *)

- ea: `0x1400cb6dc`
- end: `0x1400cb927`
- name: `?ReadDeviceExtensionTemplate@ContainerDefinition@ComputeService@@YA?AUDevice@Definition@Containers@Schema@@PEBG@Z`
- size: `587`
- prototype: `struct Schema::Containers::Definition::Device __high(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d051c`

## callees

- `0x140005360`
- `0x140009f8c`
- `0x14000ea60`
- `0x1400341ac`
- `0x1400393b8`
- `0x1400bf468`
- `0x1400c0170`
- `0x1400c0244`
- `0x1400cb6dc`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400cb78c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400cb78c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400cb759`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400cb759`
- `XmlLite!CreateXmlReader` at `0x1400cb7e4`
- `XmlLite!CreateXmlReader` at `0x1400cb7e4`

## string_xrefs

- `0x1400cb8eb`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400cb8fd`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400cb840`: `Error demarshalling from XML file`
- `0x1400cb858`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400cb8d2`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`
- `0x1400cb915`: `onecore\vm\compute\management\shared\container\definitionfiledevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall ComputeService::ContainerDefinition::ReadDeviceExtensionTemplate(
        _QWORD *a1,
        const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v5; // r9
  HRESULT v6; // eax
  int v7; // eax
  int v8; // r8d
  __int64 v9; // rcx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-39h]
  const char *hTemplateFile; // [rsp+30h] [rbp-29h]
  int v15; // [rsp+44h] [rbp-15h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v17; // [rsp+4Ch] [rbp-Dh] BYREF
  __int64 v18; // [rsp+50h] [rbp-9h]
  _QWORD *v19; // [rsp+58h] [rbp-1h]
  char v20; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v21[24]; // [rsp+68h] [rbp+Fh] BYREF
  const unsigned __int16 *v22; // [rsp+80h] [rbp+27h] BYREF
  void *ppvObject; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 v24; // [rsp+90h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v19 = a1;
  v22 = a2;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  if ( a2 && *a2 )
  {
    FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v18 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x35A,
          (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
          (const char *)LastError,
          dwCreationDisposition);
    }
    else
    {
      v18 = -1;
      if ( !CloseHandle(FileW) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x308,
          (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
          v5);
      v24 = 0;
      v15 = 1;
      v16 = 3;
      v17 = 0x80000000;
      Vml::CreateComObject<Vml::VmComFileStream,unsigned short const * &,unsigned long,int,int>(
        &v24,
        &v22,
        &v17,
        &v16,
        (unsigned int *)&v15);
      ppvObject = 0;
      v6 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
          (const char *)(unsigned int)v6,
          dwCreationDispositiona);
      v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(
             ppvObject,
             (v24 + 24) & -(__int64)(v24 != 0));
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCA,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
          (const char *)(unsigned int)v7,
          dwCreationDispositiona);
      LOBYTE(dwCreationDispositionb) = *(_BYTE *)Marshal::FromXml<Schema::Containers::Definition::Device,>(
                                                   (unsigned int)&v20,
                                                   (_DWORD)ppvObject,
                                                   v8,
                                                   (_DWORD)a1,
                                                   6);
      wil::details::in1diag3::Throw_HrIfFalseMsg(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\definitionfiledevice.cpp",
        (const char *)0x8007000DLL,
        dwCreationDispositionb,
        (bool)"Error demarshalling from XML file",
        hTemplateFile);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v21);
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      if ( v24 )
      {
        v9 = (v24 + 24) & -(__int64)(v24 != 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400cb6dc  mov     [rsp-8+arg_10], rbx
0x1400cb6e1  push    rbp
0x1400cb6e2  push    rsi
0x1400cb6e3  push    rdi
0x1400cb6e4  lea     rbp, [rsp-47h]
0x1400cb6e9  sub     rsp, 0A0h
0x1400cb6f0  mov     rax, cs:__security_cookie
0x1400cb6f7  xor     rax, rsp
0x1400cb6fa  mov     [rbp+57h+var_18], rax
0x1400cb6fe  mov     rax, rdx
0x1400cb701  mov     rbx, rcx
0x1400cb704  mov     [rbp+57h+var_58], rcx
0x1400cb708  mov     [rbp+57h+var_30], rdx
0x1400cb70c  xor     esi, esi
0x1400cb70e  mov     [rbp+57h+var_70], esi
0x1400cb711  mov     [rcx], rsi
0x1400cb714  mov     [rcx+8], rsi
0x1400cb718  mov     [rcx+10h], rsi
0x1400cb71c  mov     [rbp+57h+var_70], 1
0x1400cb723  test    rdx, rdx
0x1400cb726  jz      loc_1400CB8AD
0x1400cb72c  cmp     [rdx], si
0x1400cb72f  jz      loc_1400CB8AD
0x1400cb735  mov     [rsp+0B0h+hTemplateFile], rsi; char *
0x1400cb73a  mov     [rsp+0B0h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1400cb742  mov     [rsp+0B0h+dwCreationDisposition], 3; unsigned int
0x1400cb74a  xor     r9d, r9d; lpSecurityAttributes
0x1400cb74d  mov     edx, 80000000h; dwDesiredAccess
0x1400cb752  lea     r8d, [rsi+1]; dwShareMode
0x1400cb756  mov     rcx, rax; lpFileName
0x1400cb759  call    cs:__imp_CreateFileW
0x1400cb75f  mov     [rbp+57h+var_60], rax
0x1400cb763  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400cb767  jnz     short loc_1400CB77D
0x1400cb769  call    cs:__imp_GetLastError
0x1400cb76f  cmp     eax, 2
0x1400cb772  jnz     loc_1400CB8E4
0x1400cb778  jmp     loc_1400CB8AD
0x1400cb77d  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x1400cb785  mov     rdi, [rbp+5Fh]
0x1400cb789  mov     rcx, rax; hObject
0x1400cb78c  call    cs:__imp_CloseHandle
0x1400cb792  test    eax, eax
0x1400cb794  jz      loc_1400CB8FD
0x1400cb79a  mov     [rbp+57h+var_20], rsi
0x1400cb79e  mov     [rbp+57h+var_6C], 1
0x1400cb7a5  mov     [rbp+57h+var_68], 3
0x1400cb7ac  mov     [rbp+57h+var_64], 80000000h
0x1400cb7b3  lea     rax, [rbp+57h+var_6C]
0x1400cb7b7  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x1400cb7bc  lea     r9, [rbp+57h+var_68]
0x1400cb7c0  lea     r8, [rbp+57h+var_64]
0x1400cb7c4  lea     rdx, [rbp+57h+var_30]
0x1400cb7c8  lea     rcx, [rbp+57h+var_20]
0x1400cb7cc  call    ??$CreateComObject@VVmComFileStream@Vml@@AEAPEBGKHH@Vml@@YA?AV?$VmComPtr@VVmComFileStream@Vml@@@0@AEAPEBG$$QEAK$$QEAH2@Z; Vml::CreateComObject<Vml::VmComFileStream,ushort const * &,ulong,int,int>(ushort const * &,ulong &&,int &&,int &&)
0x1400cb7d1  nop
0x1400cb7d2  mov     [rbp+57h+ppvObject], rsi
0x1400cb7d6  xor     r8d, r8d; pMalloc
0x1400cb7d9  lea     rdx, [rbp+57h+ppvObject]; ppvObject
0x1400cb7dd  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1400cb7e4  call    cs:__imp_CreateXmlReader
0x1400cb7ea  mov     rcx, [rbp+5Fh]; this
0x1400cb7ee  test    eax, eax
0x1400cb7f0  js      loc_1400CB912
0x1400cb7f6  mov     rcx, [rbp+57h+ppvObject]
0x1400cb7fa  mov     rdx, [rbp+57h+var_20]
0x1400cb7fe  mov     r8, [rcx]
0x1400cb801  lea     rax, [rdx+18h]
0x1400cb805  neg     rdx
0x1400cb808  sbb     rdx, rdx
0x1400cb80b  and     rdx, rax
0x1400cb80e  mov     rax, [r8+18h]
0x1400cb812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cb817  mov     rcx, [rbp+5Fh]; this
0x1400cb81b  test    eax, eax
0x1400cb81d  js      loc_1400CB8CF
0x1400cb823  mov     [rsp+0B0h+dwCreationDisposition], 6
0x1400cb82b  mov     r9, rbx
0x1400cb82e  mov     rdx, [rbp+57h+ppvObject]
0x1400cb832  lea     rcx, [rbp+57h+var_50]
0x1400cb836  call    ??$FromXml@UDevice@Definition@Containers@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUIXmlReader@@PEBGPEAUDevice@Definition@Containers@Schema@@W4UnmarshalFlags@0@@Z; Marshal::FromXml<Schema::Containers::Definition::Device,>(IXmlReader *,ushort const *,Schema::Containers::Definition::Device *,Marshal::UnmarshalFlags)
0x1400cb83b  nop
0x1400cb83c  mov     rcx, [rbp+5Fh]; this
0x1400cb840  lea     rdx, aErrorDemarshal; "Error demarshalling from XML file"
0x1400cb847  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rdx; bool
0x1400cb84c  mov     al, [rax]
0x1400cb84e  mov     byte ptr [rsp+0B0h+dwCreationDisposition], al; int
0x1400cb852  mov     r9d, 8007000Dh; char *
0x1400cb858  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\management\\share"...
0x1400cb85f  mov     edx, 0D1h; void *
0x1400cb864  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400cb869  nop
0x1400cb86a  lea     rcx, [rbp+57h+var_48]
0x1400cb86e  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400cb873  nop
0x1400cb874  mov     rcx, [rbp+57h+ppvObject]
0x1400cb878  test    rcx, rcx
0x1400cb87b  jz      short loc_1400CB88A
0x1400cb87d  mov     rax, [rcx]
0x1400cb880  mov     rax, [rax+10h]
0x1400cb884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cb889  nop
0x1400cb88a  mov     rcx, [rbp+57h+var_20]
0x1400cb88e  test    rcx, rcx
0x1400cb891  jz      short loc_1400CB8AD
0x1400cb893  lea     rdx, [rcx+18h]
0x1400cb897  neg     rcx
0x1400cb89a  sbb     rcx, rcx
0x1400cb89d  and     rcx, rdx
0x1400cb8a0  mov     rdx, [rcx]
0x1400cb8a3  mov     rax, [rdx+10h]
0x1400cb8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cb8ac  nop
0x1400cb8ad  mov     rax, rbx
0x1400cb8b0  mov     rcx, [rbp+57h+var_18]
0x1400cb8b4  xor     rcx, rsp; StackCookie
0x1400cb8b7  call    __security_check_cookie
0x1400cb8bc  mov     rbx, [rsp+0B0h+arg_10]
0x1400cb8c4  add     rsp, 0A0h
0x1400cb8cb  pop     rdi
0x1400cb8cc  pop     rsi
0x1400cb8cd  pop     rbp
0x1400cb8ce  retn
0x1400cb8cf  mov     r9d, eax; char *
0x1400cb8d2  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\management\\share"...
0x1400cb8d9  mov     edx, 0CAh; void *
0x1400cb8de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400cb8e4  mov     rcx, [rbp+5Fh]; this
0x1400cb8e8  mov     r9d, eax; char *
0x1400cb8eb  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400cb8f2  mov     edx, 35Ah; void *
0x1400cb8f7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400cb8fd  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400cb904  mov     edx, 308h; void *
0x1400cb909  mov     rcx, rdi; this
0x1400cb90c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400cb912  mov     r9d, eax; char *
0x1400cb915  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\management\\share"...
0x1400cb91c  mov     edx, 0C9h; void *
0x1400cb921  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
