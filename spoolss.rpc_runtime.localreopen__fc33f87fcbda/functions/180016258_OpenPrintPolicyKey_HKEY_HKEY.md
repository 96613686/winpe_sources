# OpenPrintPolicyKey(HKEY__ *,HKEY__ * *)

- ea: `0x180016258`
- end: `0x1800162c1`
- name: `?OpenPrintPolicyKey@@YAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `105`
- prototype: `__int64 __fastcall(HKEY, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016324`

## callees

- `0x180016240`
- `0x180016258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001629b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001629b`

## pseudocode

```c
__int64 __fastcall OpenPrintPolicyKey(HKEY a1, HKEY *a2)
{
  __int64 result; // rax
  unsigned int v4; // eax
  int v5; // edx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  if ( !a2 )
    return 2147500035LL;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Printers",
         0,
         0x20019u,
         &phkResult);
  result = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v4, v5);
  if ( (int)result >= 0 )
    *a2 = phkResult;
  return result;
}

```

## disassembly

```asm
0x180016258  mov     [rsp+arg_0], rcx
0x18001625d  push    rbx
0x18001625e  sub     rsp, 30h
0x180016262  mov     [rsp+38h+arg_0], 0
0x18001626b  mov     rbx, rdx
0x18001626e  test    rdx, rdx
0x180016271  jnz     short loc_18001627A
0x180016273  mov     eax, 80004003h
0x180016278  jmp     short loc_1800162BA
0x18001627a  lea     rax, [rsp+38h+arg_0]
0x18001627f  mov     r9d, 20019h; samDesired
0x180016285  xor     r8d, r8d; ulOptions
0x180016288  mov     [rsp+38h+phkResult], rax; phkResult
0x18001628d  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x180016294  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001629b  call    cs:__imp_RegOpenKeyExW
0x1800162a2  nop     dword ptr [rax+rax+00h]
0x1800162a7  mov     ecx, eax; this
0x1800162a9  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x1800162ae  test    eax, eax
0x1800162b0  js      short loc_1800162BA
0x1800162b2  mov     rcx, [rsp+38h+arg_0]
0x1800162b7  mov     [rbx], rcx
0x1800162ba  add     rsp, 30h
0x1800162be  pop     rbx
0x1800162bf  retn
```
