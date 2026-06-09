# SP_CONTROL::DeleteParameter(_GUID *)

- ea: `0x1400a1f54`
- end: `0x1400a2047`
- name: `?DeleteParameter@SP_CONTROL@@QEAAJPEAU_GUID@@@Z`
- size: `243`
- prototype: `int(SP_CONTROL *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1400aa990`

## callees

- `0x1400a1f54`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a202d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a202d`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a1f81`
- `ntoskrnl!RtlStringFromGUID` at `0x1400a1f81`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a1fcf`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a2001`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a1fcf`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1400a2001`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a1fae`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a1fae`
- `ntoskrnl!ZwClose` at `0x1400a201c`
- `ntoskrnl!ZwClose` at `0x1400a201c`

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
0x1400a1f54  mov     rax, rsp
0x1400a1f57  mov     [rax+10h], rbx
0x1400a1f5b  mov     [rax+8], rcx
0x1400a1f5f  push    rdi
0x1400a1f60  sub     rsp, 40h
0x1400a1f64  mov     rdi, cs:WPP_MAIN_CB.DeviceExtension
0x1400a1f6b  mov     rcx, rdx; Guid
0x1400a1f6e  xorps   xmm0, xmm0
0x1400a1f71  mov     qword ptr [rax+8], 0
0x1400a1f79  lea     rdx, [rax-18h]; GuidString
0x1400a1f7d  movups  xmmword ptr [rax-18h], xmm0
0x1400a1f81  call    cs:__imp_RtlStringFromGUID
0x1400a1f88  nop     dword ptr [rax+rax+00h]
0x1400a1f8d  mov     ebx, eax
0x1400a1f8f  test    eax, eax
0x1400a1f91  js      short loc_1400A2012
0x1400a1f93  mov     rcx, [rdi+8]
0x1400a1f97  lea     rax, [rsp+48h+Path]
0x1400a1f9c  xor     r9d, r9d
0x1400a1f9f  mov     [rsp+48h+var_28], rax
0x1400a1fa4  mov     r8d, 20006h
0x1400a1faa  lea     edx, [r9+1]
0x1400a1fae  call    cs:__imp_IoOpenDriverRegistryKey
0x1400a1fb5  nop     dword ptr [rax+rax+00h]
0x1400a1fba  mov     ebx, eax
0x1400a1fbc  test    eax, eax
0x1400a1fbe  js      short loc_1400A2012
0x1400a1fc0  mov     r8, [rsp+48h+UnicodeString.Buffer]; ValueName
0x1400a1fc5  mov     ecx, 40000000h; RelativeTo
0x1400a1fca  mov     rdx, [rsp+48h+Path]; Path
0x1400a1fcf  call    cs:__imp_RtlDeleteRegistryValue
0x1400a1fd6  nop     dword ptr [rax+rax+00h]
0x1400a1fdb  mov     edx, 80000000h
0x1400a1fe0  mov     ebx, eax
0x1400a1fe2  add     eax, edx
0x1400a1fe4  test    edx, eax
0x1400a1fe6  jnz     short loc_1400A1FF0
0x1400a1fe8  cmp     ebx, 0C0000034h
0x1400a1fee  jnz     short loc_1400A2012
0x1400a1ff0  mov     r8, [rsp+48h+UnicodeString.Buffer]; ValueName
0x1400a1ff5  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a1ffc  mov     ecx, 1; RelativeTo
0x1400a2001  call    cs:__imp_RtlDeleteRegistryValue
0x1400a2008  nop     dword ptr [rax+rax+00h]
0x1400a200d  test    eax, eax
0x1400a200f  cmovns  ebx, eax
0x1400a2012  mov     rcx, [rsp+48h+Path]; Handle
0x1400a2017  test    rcx, rcx
0x1400a201a  jz      short loc_1400A2028
0x1400a201c  call    cs:__imp_ZwClose
0x1400a2023  nop     dword ptr [rax+rax+00h]
0x1400a2028  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x1400a202d  call    cs:__imp_RtlFreeUnicodeString
0x1400a2034  nop     dword ptr [rax+rax+00h]
0x1400a2039  mov     eax, ebx
0x1400a203b  mov     rbx, [rsp+48h+arg_8]
0x1400a2040  add     rsp, 40h
0x1400a2044  pop     rdi
0x1400a2045  retn
```
