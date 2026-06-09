# CWHost::CWHost(_GUID const *,IUnknown *)

- ea: `0x18000fb50`
- end: `0x18000fc52`
- name: `??0CWHost@@AEAA@PEBU_GUID@@PEAUIUnknown@@@Z`
- size: `258`
- prototype: `CWHost *(CWHost *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fdec`

## callees

- `0x18000ae04`
- `0x18000fb50`
- `0x18001c19c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fc3a`

## string_xrefs

- `0x18000fc0b`: `XWCanRegisterTask`
- `0x18000fc1b`: `XWCanUnregisterTask`
- `0x18000fc2f`: `XWOnTaskEvent`

## pseudocode

```c
CWHost *__fastcall CWHost::CWHost(CWHost *this, const struct _GUID *a2, struct IUnknown *a3)
{
  struct IUnknown *v3; // rax
  HMODULE *v5; // rdi
  int WizardCommonModule; // eax
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CUnknown::`vftable';
  v3 = (struct IUnknown *)this;
  if ( a3 )
    v3 = a3;
  *((_QWORD *)this + 2) = v3;
  _InterlockedIncrement(&CUnknown::s_cActiveComponents);
  v5 = (HMODULE *)((char *)this + 48);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *(_QWORD *)this = &CWHost::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWHost::`vftable'{for `IXWizardHostEvent'};
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 6) = 0;
  *((struct _GUID *)this + 2) = *a2;
  WizardCommonModule = HrGetWizardCommonModule(a2, (HINSTANCE *)this + 6);
  if ( WizardCommonModule >= 0 )
  {
    ProcAddress = GetProcAddress(*v5, "XWCanRegisterTask");
    v8 = *v5;
    *((_QWORD *)this + 7) = ProcAddress;
    v9 = GetProcAddress(v8, "XWCanUnregisterTask");
    v10 = *v5;
    *((_QWORD *)this + 8) = v9;
    *((_QWORD *)this + 9) = GetProcAddress(v10, "XWOnTaskEvent");
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_80c7ba19459d37aeb7a4510588c43e20_Traceguids,
      (unsigned int)WizardCommonModule);
  }
  return this;
}

```

## disassembly

```asm
0x18000fb50  mov     [rsp+arg_0], rbx
0x18000fb55  push    rdi
0x18000fb56  sub     rsp, 20h
0x18000fb5a  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x18000fb61  mov     dword ptr [rcx+8], 1
0x18000fb68  mov     [rcx], rax
0x18000fb6b  test    r8, r8
0x18000fb6e  mov     rax, rcx
0x18000fb71  mov     r9, rdx
0x18000fb74  cmovnz  rax, r8
0x18000fb78  mov     rbx, rcx
0x18000fb7b  mov     [rcx+10h], rax
0x18000fb7f  lock inc cs:?s_cActiveComponents@CUnknown@@0JA; long CUnknown::s_cActiveComponents
0x18000fb86  lea     rdi, [rcx+30h]
0x18000fb8a  mov     qword ptr [rcx+38h], 0
0x18000fb92  mov     qword ptr [rcx+40h], 0
0x18000fb9a  lea     rax, ??_7CWHost@@6BCUnknown@@@; const CWHost::`vftable'{for `CUnknown'}
0x18000fba1  mov     [rcx], rax
0x18000fba4  lea     rax, ??_7CWHost@@6BIXWizardHostEvent@@@; const CWHost::`vftable'{for `IXWizardHostEvent'}
0x18000fbab  mov     [rcx+18h], rax
0x18000fbaf  mov     qword ptr [rcx+48h], 0
0x18000fbb7  mov     qword ptr [rdi], 0
0x18000fbbe  movups  xmm0, xmmword ptr [rdx]
0x18000fbc1  mov     rdx, rdi; HINSTANCE *
0x18000fbc4  movdqu  xmmword ptr [rcx+20h], xmm0
0x18000fbc9  mov     rcx, r9; struct _GUID *
0x18000fbcc  call    ?HrGetWizardCommonModule@@YAJPEBU_GUID@@PEAPEAUHINSTANCE__@@@Z; HrGetWizardCommonModule(_GUID const *,HINSTANCE__ * *)
0x18000fbd1  test    eax, eax
0x18000fbd3  jns     short loc_18000FC08
0x18000fbd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbdc  lea     rdx, WPP_GLOBAL_Control
0x18000fbe3  cmp     rcx, rdx
0x18000fbe6  jz      short loc_18000FC44
0x18000fbe8  test    byte ptr [rcx+1Ch], 4
0x18000fbec  jz      short loc_18000FC44
0x18000fbee  mov     rcx, [rcx+10h]
0x18000fbf2  lea     r8, WPP_80c7ba19459d37aeb7a4510588c43e20_Traceguids
0x18000fbf9  mov     edx, 0Ah
0x18000fbfe  mov     r9d, eax
0x18000fc01  call    WPP_SF_d
0x18000fc06  jmp     short loc_18000FC44
0x18000fc08  mov     rcx, [rdi]; hModule
0x18000fc0b  lea     rdx, aXwcanregistert; "XWCanRegisterTask"
0x18000fc12  call    cs:__imp_GetProcAddress
0x18000fc18  mov     rcx, [rdi]; hModule
0x18000fc1b  lea     rdx, aXwcanunregiste_0; "XWCanUnregisterTask"
0x18000fc22  mov     [rbx+38h], rax
0x18000fc26  call    cs:__imp_GetProcAddress
0x18000fc2c  mov     rcx, [rdi]; hModule
0x18000fc2f  lea     rdx, aXwontaskevent; "XWOnTaskEvent"
0x18000fc36  mov     [rbx+40h], rax
0x18000fc3a  call    cs:__imp_GetProcAddress
0x18000fc40  mov     [rbx+48h], rax
0x18000fc44  mov     rax, rbx
0x18000fc47  mov     rbx, [rsp+28h+arg_0]
0x18000fc4c  add     rsp, 20h
0x18000fc50  pop     rdi
0x18000fc51  retn
```
