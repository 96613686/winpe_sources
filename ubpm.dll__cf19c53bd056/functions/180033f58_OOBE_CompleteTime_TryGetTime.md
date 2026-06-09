# OOBE::CompleteTime::TryGetTime

- ea: `0x180033f58`
- end: `0x18003402c`
- name: `OOBE::CompleteTime::TryGetTime`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b670`
- `0x1800344a0`

## callees

- `0x180033244`
- `0x18003370c`
- `0x180033f58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033fbb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034008`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033fbb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034008`

## string_xrefs

- `0x180033f9e`: `OOBECompleteTimestamp`

## pseudocode

```c
__int64 __fastcall OOBE::CompleteTime::TryGetTime(bool *a1, _OWORD *a2)
{
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  *a1 = 0;
  pcbData = 16;
  hkey = 0;
  *a2 = 0;
  if ( (int)OOBE::CompleteTime::details::GetOOBECompleteKey((unsigned __int16 *)&hkey, (const unsigned __int16 *)a2) >= 0 )
    *a1 = RegGetValueW(hkey, 0, L"OOBECompleteTimestamp", 0x20000008u, 0, a2, &pcbData) == 0;
  if ( !*a1 )
  {
    pcbData = 16;
    *a1 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            L"EndTimeStamp",
            0x20000008u,
            0,
            a2,
            &pcbData) == 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x180033f58  mov     rax, rsp
0x180033f5b  mov     [rax+10h], rbx
0x180033f5f  push    rdi
0x180033f60  sub     rsp, 40h
0x180033f64  mov     rbx, rcx
0x180033f67  mov     byte ptr [rcx], 0
0x180033f6a  xorps   xmm0, xmm0
0x180033f6d  mov     dword ptr [rax+8], 10h
0x180033f74  lea     rcx, [rax+18h]; phkResult
0x180033f78  mov     qword ptr [rax+18h], 0
0x180033f80  movups  xmmword ptr [rdx], xmm0
0x180033f83  mov     rdi, rdx
0x180033f86  call    OOBE__CompleteTime__details__GetOOBECompleteKey
0x180033f8b  test    eax, eax
0x180033f8d  js      short loc_180033FC8
0x180033f8f  mov     rcx, [rsp+48h+hkey]; hkey
0x180033f94  lea     rax, [rsp+48h+arg_0]
0x180033f99  mov     [rsp+48h+pcbData], rax; pcbData
0x180033f9e  lea     r8, aOobecompleteti; "OOBECompleteTimestamp"
0x180033fa5  mov     [rsp+48h+pvData], rdi; pvData
0x180033faa  mov     r9d, 20000008h; dwFlags
0x180033fb0  xor     edx, edx; lpSubKey
0x180033fb2  mov     [rsp+48h+pdwType], 0; pdwType
0x180033fbb  call    cs:__imp_RegGetValueW
0x180033fc1  test    eax, eax
0x180033fc3  setz    al
0x180033fc6  mov     [rbx], al
0x180033fc8  cmp     byte ptr [rbx], 0
0x180033fcb  jnz     short loc_180034015
0x180033fcd  lea     rax, [rsp+48h+arg_0]
0x180033fd2  mov     [rsp+48h+arg_0], 10h
0x180033fda  mov     [rsp+48h+pcbData], rax; pcbData
0x180033fdf  lea     r8, aEndtimestamp; "EndTimeStamp"
0x180033fe6  mov     [rsp+48h+pvData], rdi; pvData
0x180033feb  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180033ff2  mov     r9d, 20000008h; dwFlags
0x180033ff8  mov     [rsp+48h+pdwType], 0; pdwType
0x180034001  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180034008  call    cs:__imp_RegGetValueW
0x18003400e  test    eax, eax
0x180034010  setz    al
0x180034013  mov     [rbx], al
0x180034015  lea     rcx, [rsp+48h+hkey]
0x18003401a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003401f  mov     rbx, [rsp+48h+arg_8]
0x180034024  xor     eax, eax
0x180034026  add     rsp, 40h
0x18003402a  pop     rdi
0x18003402b  retn
```
