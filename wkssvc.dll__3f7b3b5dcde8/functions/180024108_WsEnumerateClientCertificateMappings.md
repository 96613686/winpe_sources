# WsEnumerateClientCertificateMappings

- ea: `0x180024108`
- end: `0x1800241f7`
- name: `WsEnumerateClientCertificateMappings`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800247d8`

## callees

- `0x180022b7c`
- `0x180024108`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800241f0`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180024191`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180024191`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002411d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002411d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002419c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002419c`

## pseudocode

```c
ULONG __fastcall WsEnumerateClientCertificateMappings(__int64 a1)
{
  _DWORD *v2; // rbx
  NTSTATUS RegistryValues; // edi

  v2 = LocalAlloc(0x40u, 0x70u);
  if ( v2 )
  {
    v2[2] = 16;
    *(_QWORD *)v2 = EnumerateServerCertificate;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    v2[8] = 0;
    *((_QWORD *)v2 + 5) = 0;
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v2[16] = 0;
    *((_QWORD *)v2 + 9) = 0;
    RegistryValues = RtlQueryRegistryValuesEx(0, &Path, v2, a1, 0);
    LocalFree(v2);
    if ( RegistryValues >= 0 )
      return RtlNtStatusToDosError(RegistryValues);
  }
  else
  {
    RegistryValues = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
      (unsigned int)RegistryValues);
  }
  return RtlNtStatusToDosError(RegistryValues);
}

```

## disassembly

```asm
0x180024108  mov     [rsp+arg_0], rbx
0x18002410d  push    rdi
0x18002410e  sub     rsp, 30h
0x180024112  mov     edx, 70h ; 'p'; uBytes
0x180024117  mov     rdi, rcx
0x18002411a  lea     ecx, [rdx-30h]; uFlags
0x18002411d  call    cs:__imp_LocalAlloc
0x180024123  mov     rbx, rax
0x180024126  test    rax, rax
0x180024129  jz      short loc_1800241A8
0x18002412b  lea     rax, EnumerateServerCertificate
0x180024132  mov     dword ptr [rbx+8], 10h
0x180024139  mov     r9, rdi
0x18002413c  mov     [rbx], rax
0x18002413f  mov     r8, rbx
0x180024142  mov     qword ptr [rbx+10h], 0
0x18002414a  lea     rdx, Path
0x180024151  mov     qword ptr [rbx+18h], 0
0x180024159  xor     ecx, ecx
0x18002415b  mov     dword ptr [rbx+20h], 0
0x180024162  mov     qword ptr [rbx+28h], 0
0x18002416a  mov     dword ptr [rbx+30h], 0
0x180024171  mov     qword ptr [rbx+38h], 0
0x180024179  mov     dword ptr [rbx+40h], 0
0x180024180  mov     qword ptr [rbx+48h], 0
0x180024188  mov     [rsp+38h+var_18], 0
0x180024191  call    cs:__imp_RtlQueryRegistryValuesEx
0x180024197  mov     rcx, rbx; hMem
0x18002419a  mov     edi, eax
0x18002419c  call    cs:__imp_LocalFree
0x1800241a2  test    edi, edi
0x1800241a4  jns     short loc_1800241E4
0x1800241a6  jmp     short loc_1800241AD
0x1800241a8  mov     edi, 0C000009Ah
0x1800241ad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800241b4  lea     rax, WPP_GLOBAL_Control
0x1800241bb  cmp     rcx, rax
0x1800241be  jz      short loc_1800241E4
0x1800241c0  test    byte ptr [rcx+1Ch], 2
0x1800241c4  jz      short loc_1800241E4
0x1800241c6  cmp     byte ptr [rcx+19h], 1
0x1800241ca  jb      short loc_1800241E4
0x1800241cc  mov     rcx, [rcx+10h]
0x1800241d0  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800241d7  mov     edx, 48h ; 'H'
0x1800241dc  mov     r9d, edi
0x1800241df  call    WPP_SF_d
0x1800241e4  mov     ecx, edi
0x1800241e6  mov     rbx, [rsp+38h+arg_0]
0x1800241eb  add     rsp, 30h
0x1800241ef  pop     rdi
0x1800241f0  jmp     cs:__imp_RtlNtStatusToDosError
```
