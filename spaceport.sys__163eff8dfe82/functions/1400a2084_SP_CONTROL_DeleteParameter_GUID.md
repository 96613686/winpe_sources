# SP_CONTROL::DeleteParameter(_GUID *)

- ea: `0x1400a2084`
- end: `0x1400a2177`
- name: `?DeleteParameter@SP_CONTROL@@QEAAJPEAU_GUID@@@Z`
- size: `243`
- prototype: `int(SP_CONTROL *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1400aab30`

## callees

- `0x1400a2084`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a215d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a215d`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a20b1`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a20b1`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a20ff`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a2131`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a20ff`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a2131`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a20de`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a20de`
- `ntoskrnl!ZwClose` at `0x1400a214c`
- `ntoskrnl!ZwClose` at `0x1400a214c`

## pseudocode

```c
__int64 __fastcall SP_CONTROL::DeleteParameter(SP_CONTROL *this, struct _GUID *a2)
{
  _QWORD *DeviceExtension; // rdi
  NTSTATUS v3; // ebx
  NTSTATUS v4; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-18h] BYREF

  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  UnicodeString = 0;
  v3 = RtlStringFromGUID(a2, &UnicodeString);
  if ( v3 >= 0 )
  {
    v3 = IoOpenDriverRegistryKey(DeviceExtension[1], 1, 131078);
    if ( v3 >= 0 )
    {
      v3 = RtlDeleteRegistryValue(0x40000000u, 0, UnicodeString.Buffer);
      if ( (int)(v3 + 0x80000000) < 0 || v3 == -1073741772 )
      {
        v4 = RtlDeleteRegistryValue(1u, L"Spaceport\\Parameters", UnicodeString.Buffer);
        if ( v4 >= 0 )
          v3 = v4;
      }
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400a2084  mov     rax, rsp
0x1400a2087  mov     [rax+10h], rbx
0x1400a208b  mov     [rax+8], rcx
0x1400a208f  push    rdi
0x1400a2090  sub     rsp, 40h
0x1400a2094  mov     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a209b  mov     rcx, rdx; Guid
0x1400a209e  xorps   xmm0, xmm0
0x1400a20a1  mov     qword ptr [rax+8], 0
0x1400a20a9  lea     rdx, [rax-18h]; GuidString
0x1400a20ad  movups  xmmword ptr [rax-18h], xmm0
0x1400a20b1  call    cs:__imp_RtlStringFromGUID
0x1400a20b8  nop     dword ptr [rax+rax+00h]
0x1400a20bd  mov     ebx, eax
0x1400a20bf  test    eax, eax
0x1400a20c1  js      short loc_1400A2142
0x1400a20c3  mov     rcx, [rdi+8]
0x1400a20c7  lea     rax, [rsp+48h+Path]
0x1400a20cc  xor     r9d, r9d
0x1400a20cf  mov     [rsp+48h+var_28], rax
0x1400a20d4  mov     r8d, 20006h
0x1400a20da  lea     edx, [r9+1]
0x1400a20de  call    cs:__imp_IoOpenDriverRegistryKey
0x1400a20e5  nop     dword ptr [rax+rax+00h]
0x1400a20ea  mov     ebx, eax
0x1400a20ec  test    eax, eax
0x1400a20ee  js      short loc_1400A2142
0x1400a20f0  mov     r8, [rsp+48h+UnicodeString.Buffer]; ValueName
0x1400a20f5  mov     ecx, 40000000h; RelativeTo
0x1400a20fa  mov     rdx, [rsp+48h+Path]; Path
0x1400a20ff  call    cs:__imp_RtlDeleteRegistryValue
0x1400a2106  nop     dword ptr [rax+rax+00h]
0x1400a210b  mov     edx, 80000000h
0x1400a2110  mov     ebx, eax
0x1400a2112  add     eax, edx
0x1400a2114  test    edx, eax
0x1400a2116  jnz     short loc_1400A2120
0x1400a2118  cmp     ebx, 0C0000034h
0x1400a211e  jnz     short loc_1400A2142
0x1400a2120  mov     r8, [rsp+48h+UnicodeString.Buffer]; ValueName
0x1400a2125  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a212c  mov     ecx, 1; RelativeTo
0x1400a2131  call    cs:__imp_RtlDeleteRegistryValue
0x1400a2138  nop     dword ptr [rax+rax+00h]
0x1400a213d  test    eax, eax
0x1400a213f  cmovns  ebx, eax
0x1400a2142  mov     rcx, [rsp+48h+Path]; Handle
0x1400a2147  test    rcx, rcx
0x1400a214a  jz      short loc_1400A2158
0x1400a214c  call    cs:__imp_ZwClose
0x1400a2153  nop     dword ptr [rax+rax+00h]
0x1400a2158  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x1400a215d  call    cs:__imp_RtlFreeUnicodeString
0x1400a2164  nop     dword ptr [rax+rax+00h]
0x1400a2169  mov     eax, ebx
0x1400a216b  mov     rbx, [rsp+48h+arg_8]
0x1400a2170  add     rsp, 40h
0x1400a2174  pop     rdi
0x1400a2175  retn
```
