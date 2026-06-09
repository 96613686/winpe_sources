# WsEnumerateClientCertificateMappings

- ea: `0x180025c44`
- end: `0x180025d4e`
- name: `WsEnumerateClientCertificateMappings`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800263bc`

## callees

- `0x180024550`
- `0x180025c44`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180025d42`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180025cd7`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180025cd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025c59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025c59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ce8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ce8`

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
      &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
      (unsigned int)RegistryValues);
  }
  return RtlNtStatusToDosError(RegistryValues);
}

```

## disassembly

```asm
0x180025c44  mov     [rsp+arg_0], rbx
0x180025c49  push    rdi
0x180025c4a  sub     rsp, 30h
0x180025c4e  mov     edx, 70h ; 'p'; uBytes
0x180025c53  mov     rdi, rcx
0x180025c56  lea     ecx, [rdx-30h]; uFlags
0x180025c59  call    cs:__imp_LocalAlloc
0x180025c60  nop     dword ptr [rax+rax+00h]
0x180025c65  mov     rbx, rax
0x180025c68  test    rax, rax
0x180025c6b  jz      loc_180025CFA
0x180025c71  lea     rax, EnumerateServerCertificate
0x180025c78  mov     dword ptr [rbx+8], 10h
0x180025c7f  mov     r9, rdi
0x180025c82  mov     [rbx], rax
0x180025c85  mov     r8, rbx
0x180025c88  mov     qword ptr [rbx+10h], 0
0x180025c90  lea     rdx, Path
0x180025c97  mov     qword ptr [rbx+18h], 0
0x180025c9f  xor     ecx, ecx
0x180025ca1  mov     dword ptr [rbx+20h], 0
0x180025ca8  mov     qword ptr [rbx+28h], 0
0x180025cb0  mov     dword ptr [rbx+30h], 0
0x180025cb7  mov     qword ptr [rbx+38h], 0
0x180025cbf  mov     dword ptr [rbx+40h], 0
0x180025cc6  mov     qword ptr [rbx+48h], 0
0x180025cce  mov     [rsp+38h+var_18], 0
0x180025cd7  call    cs:__imp_RtlQueryRegistryValuesEx
0x180025cde  nop     dword ptr [rax+rax+00h]
0x180025ce3  mov     rcx, rbx; hMem
0x180025ce6  mov     edi, eax
0x180025ce8  call    cs:__imp_LocalFree
0x180025cef  nop     dword ptr [rax+rax+00h]
0x180025cf4  test    edi, edi
0x180025cf6  jns     short loc_180025D36
0x180025cf8  jmp     short loc_180025CFF
0x180025cfa  mov     edi, 0C000009Ah
0x180025cff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025d06  lea     rax, WPP_GLOBAL_Control
0x180025d0d  cmp     rcx, rax
0x180025d10  jz      short loc_180025D36
0x180025d12  test    byte ptr [rcx+1Ch], 2
0x180025d16  jz      short loc_180025D36
0x180025d18  cmp     byte ptr [rcx+19h], 1
0x180025d1c  jb      short loc_180025D36
0x180025d1e  mov     rcx, [rcx+10h]
0x180025d22  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180025d29  mov     edx, 48h ; 'H'
0x180025d2e  mov     r9d, edi
0x180025d31  call    WPP_SF_d
0x180025d36  mov     ecx, edi
0x180025d38  mov     rbx, [rsp+38h+arg_0]
0x180025d3d  add     rsp, 30h
0x180025d41  pop     rdi
0x180025d42  jmp     cs:__imp_RtlNtStatusToDosError
```
