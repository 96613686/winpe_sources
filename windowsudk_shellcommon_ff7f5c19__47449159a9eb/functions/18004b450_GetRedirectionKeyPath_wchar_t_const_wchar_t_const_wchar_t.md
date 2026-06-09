# GetRedirectionKeyPath(wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18004b450`
- end: `0x18004b527`
- name: `?GetRedirectionKeyPath@@YAJPEB_W0PEAPEA_W@Z`
- size: `215`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b2d4`

## callees

- `0x18004b450`
- `0x1800e34bc`
- `0x1803bfc00`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004b48b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004b4c9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004b48b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004b4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b4ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b4ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b49c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b49c`

## string_xrefs

- `0x18004b481`: `OOBECompleteTimestamp`
- `0x18004b4c2`: `OOBECompleteTimestamp`
- `0x18004b473`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x18004b4af`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`

## pseudocode

```c
__int64 __fastcall GetRedirectionKeyPath(const wchar_t *a1, const wchar_t *a2, wchar_t **a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  LPVOID v7; // rax
  void *v8; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int *p_cb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int cb; // [rsp+48h] [rbp+10h] BYREF
  int cb_4; // [rsp+4Ch] [rbp+14h]

  cb_4 = HIDWORD(a2);
  cb = 0;
  p_cb = &cb;
  *a3 = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"OOBECompleteTimestamp",
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                       a3,
                       0) == 234 )
  {
    v7 = CoTaskMemAlloc(cb);
    v8 = v7;
    if ( v7 )
    {
      LODWORD(p_cb) = 0;
      if ( (unsigned int)GetPersistedRegistryLocationW(
                           L"OOBECompleteTimestamp",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                           v7,
                           cb) )
        CoTaskMemFree(v8);
      else
        *a3 = (wchar_t *)v8;
    }
  }
  if ( *a3 )
    return 0;
  v10 = _AllocStringWorker<CTCoAllocPolicy>(v5, v4, v6, 68);
  v11 = v10;
  if ( v10 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
    (const char *)(unsigned int)v10,
    (int)p_cb);
  return v11;
}

```

## disassembly

```asm
0x18004b450  mov     rax, rsp
0x18004b453  mov     [rax+8], rbx
0x18004b457  mov     [rax+10h], rdx
0x18004b45b  push    rdi
0x18004b45c  sub     rsp, 30h
0x18004b460  mov     dword ptr [rax+10h], 0
0x18004b467  lea     rax, [rax+10h]
0x18004b46b  xor     r9d, r9d
0x18004b46e  mov     qword ptr [rsp+38h+var_18], rax
0x18004b473  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004b47a  mov     qword ptr [r8], 0
0x18004b481  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x18004b488  mov     rdi, r8
0x18004b48b  call    cs:__imp_GetPersistedRegistryLocationW
0x18004b491  cmp     eax, 0EAh
0x18004b496  jnz     short loc_18004B4D6
0x18004b498  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x18004b49c  call    cs:__imp_CoTaskMemAlloc
0x18004b4a2  mov     rbx, rax
0x18004b4a5  test    rax, rax
0x18004b4a8  jz      short loc_18004B4D6
0x18004b4aa  mov     r9d, dword ptr [rsp+38h+cb]
0x18004b4af  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004b4b6  mov     r8, rax
0x18004b4b9  mov     qword ptr [rsp+38h+var_18], 0; int
0x18004b4c2  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x18004b4c9  call    cs:__imp_GetPersistedRegistryLocationW
0x18004b4cf  test    eax, eax
0x18004b4d1  jnz     short loc_18004B4E9
0x18004b4d3  mov     [rdi], rbx
0x18004b4d6  cmp     qword ptr [rdi], 0
0x18004b4da  jz      short loc_18004B4F4
0x18004b4dc  xor     eax, eax
0x18004b4de  mov     rbx, [rsp+38h+arg_0]
0x18004b4e3  add     rsp, 30h
0x18004b4e7  pop     rdi
0x18004b4e8  retn
0x18004b4e9  mov     rcx, rbx; pv
0x18004b4ec  call    cs:__imp_CoTaskMemFree
0x18004b4f2  jmp     short loc_18004B4D6
0x18004b4f4  mov     r9d, 44h ; 'D'
0x18004b4fa  mov     [rsp+38h+var_10], rdi
0x18004b4ff  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEB_W_K2PEAPEA_W@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,wchar_t const *,unsigned __int64,unsigned __int64,wchar_t * *)
0x18004b504  mov     ebx, eax
0x18004b506  test    eax, eax
0x18004b508  jns     short loc_18004B4DC
0x18004b50a  mov     rcx, [rsp+38h]; this
0x18004b50f  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x18004b516  mov     r9d, eax; char *
0x18004b519  mov     edx, 2Eh ; '.'; void *
0x18004b51e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b523  mov     eax, ebx
0x18004b525  jmp     short loc_18004B4DE
```
