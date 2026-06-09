# UwfServicingEnableHelperService(UWF_CONFIG_INTERFACE *,bool,bool)

- ea: `0x1800032c4`
- end: `0x180003350`
- name: `?UwfServicingEnableHelperService@@YAJPEAUUWF_CONFIG_INTERFACE@@_N1@Z`
- size: `140`
- prototype: `int __fastcall(struct UWF_CONFIG_INTERFACE *, __int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000370c`

## callees

- `0x1800032c4`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180003308`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180003308`

## string_xrefs

- `0x1800032fa`: `System\CurrentControlSet\Services\UwfServicingSvc`
- `0x180003332`: `HKLM\System\CurrentControlSet\Services\UwfServicingSvc`

## pseudocode

```c
int __fastcall UwfServicingEnableHelperService(struct UWF_CONFIG_INTERFACE *a1, __int64 a2, char a3)
{
  int result; // eax
  bool v6; // sf
  int lpData; // [rsp+48h] [rbp+10h] BYREF

  lpData = 2;
  result = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\UwfServicingSvc",
             L"Start",
             4u,
             &lpData,
             4u);
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( !v6 && a3 )
  {
    if ( a1 )
      return (*(__int64 (__fastcall **)(struct UWF_CONFIG_INTERFACE *, const wchar_t *, const WCHAR *))(*(_QWORD *)a1 + 16LL))(
               a1,
               L"HKLM\\System\\CurrentControlSet\\Services\\UwfServicingSvc",
               L"Start");
  }
  return result;
}

```

## disassembly

```asm
0x1800032c4  mov     rax, rsp
0x1800032c7  mov     [rax+8], rbx
0x1800032cb  mov     [rax+10h], dl
0x1800032ce  push    rdi
0x1800032cf  sub     rsp, 30h
0x1800032d3  mov     r9d, 4; dwType
0x1800032d9  mov     dword ptr [rax+10h], 2
0x1800032e0  mov     [rax-10h], r9d
0x1800032e4  lea     rax, [rax+10h]
0x1800032e8  mov     dil, r8b
0x1800032eb  mov     [rsp+38h+lpData], rax; lpData
0x1800032f0  mov     rbx, rcx
0x1800032f3  lea     r8, aStart; "Start"
0x1800032fa  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Uw"...
0x180003301  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003308  call    cs:__imp_RegSetKeyValueW
0x18000330e  test    eax, eax
0x180003310  jle     short loc_18000331C
0x180003312  movzx   eax, ax
0x180003315  or      eax, 80070000h
0x18000331a  test    eax, eax
0x18000331c  js      short loc_180003345
0x18000331e  test    dil, dil
0x180003321  jz      short loc_180003345
0x180003323  test    rbx, rbx
0x180003326  jz      short loc_180003345
0x180003328  mov     rax, [rbx]
0x18000332b  lea     r8, aStart; "Start"
0x180003332  lea     rdx, aHklmSystemCurr; "HKLM\\System\\CurrentControlSet\\Servic"...
0x180003339  mov     rcx, rbx
0x18000333c  mov     rax, [rax+10h]
0x180003340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003345  mov     rbx, [rsp+38h+arg_0]
0x18000334a  add     rsp, 30h
0x18000334e  pop     rdi
0x18000334f  retn
```
