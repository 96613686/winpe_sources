# _SetWinVer(HINSTANCE__ *)

- ea: `0x1400072e0`
- end: `0x140007374`
- name: `?_SetWinVer@@YAXPEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `void __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140007798`

## callees

- `0x1400072e0`

## import_xrefs

- `imagehlp!ImageDirectoryEntryToData` at `0x14000734e`
- `imagehlp!ImageDirectoryEntryToData` at `0x14000734e`
- `ntdll!RtlImageNtHeader` at `0x1400072f3`
- `ntdll!RtlImageNtHeader` at `0x1400072f3`

## pseudocode

```c
void __fastcall _SetWinVer(HINSTANCE a1)
{
  struct _PEB *v1; // rbx
  PIMAGE_NT_HEADERS v2; // rax
  _WORD *v3; // rax
  USHORT v4; // ax
  ULONG Size; // [rsp+38h] [rbp+10h] BYREF

  v1 = NtCurrentPeb();
  v2 = RtlImageNtHeader(a1);
  if ( v2->FileHeader.SizeOfOptionalHeader && v2->OptionalHeader.Win32VersionValue )
  {
    v1->OSMajorVersion = LOBYTE(v2->OptionalHeader.Win32VersionValue);
    v1->OSMinorVersion = BYTE1(v2->OptionalHeader.Win32VersionValue);
    v1->OSBuildNumber = HIWORD(v2->OptionalHeader.Win32VersionValue);
    v1->OSPlatformId = (v2->OptionalHeader.Win32VersionValue ^ 0xBFFFFFFF) >> 30;
  }
  Size = 0;
  v3 = ImageDirectoryEntryToData(v1->ImageBaseAddress, 1u, 0xAu, &Size);
  if ( v3 )
  {
    v4 = v3[38];
    if ( v4 )
      v1->OSCSDVersion = v4;
  }
}

```

## disassembly

```asm
0x1400072e0  mov     [rsp+arg_0], rbx
0x1400072e5  push    rdi
0x1400072e6  sub     rsp, 20h
0x1400072ea  mov     rbx, gs:60h
0x1400072f3  call    cs:__imp_RtlImageNtHeader
0x1400072f9  xor     edi, edi
0x1400072fb  mov     rdx, rax
0x1400072fe  cmp     [rax+14h], di
0x140007302  jz      short loc_140007339
0x140007304  cmp     [rax+4Ch], edi
0x140007307  jz      short loc_140007339
0x140007309  movzx   ecx, byte ptr [rax+4Ch]
0x14000730d  mov     [rbx+118h], ecx
0x140007313  movzx   ecx, byte ptr [rax+4Dh]
0x140007317  mov     [rbx+11Ch], ecx
0x14000731d  movzx   eax, word ptr [rax+4Eh]
0x140007321  mov     [rbx+120h], ax
0x140007328  mov     eax, [rdx+4Ch]
0x14000732b  xor     eax, 0BFFFFFFFh
0x140007330  shr     eax, 1Eh
0x140007333  mov     [rbx+124h], eax
0x140007339  mov     [rsp+28h+Size], edi
0x14000733d  lea     r9, [rsp+28h+Size]; Size
0x140007342  mov     rcx, [rbx+10h]; Base
0x140007346  mov     r8d, 0Ah; DirectoryEntry
0x14000734c  mov     dl, 1; MappedAsImage
0x14000734e  call    cs:__imp_ImageDirectoryEntryToData
0x140007354  test    rax, rax
0x140007357  jz      short loc_140007369
0x140007359  movzx   eax, word ptr [rax+4Ch]
0x14000735d  test    ax, ax
0x140007360  jz      short loc_140007369
0x140007362  mov     [rbx+122h], ax
0x140007369  mov     rbx, [rsp+28h+arg_0]
0x14000736e  add     rsp, 20h
0x140007372  pop     rdi
0x140007373  retn
```
