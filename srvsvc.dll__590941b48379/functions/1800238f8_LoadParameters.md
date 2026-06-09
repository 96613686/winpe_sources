# LoadParameters

- ea: `0x1800238f8`
- end: `0x1800239eb`
- name: `LoadParameters`
- size: `243`
- prototype: `ULONG __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180014880`
- `0x180015500`

## callees

- `0x180020de8`
- `0x1800238f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002390d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002390d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002398b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002398b`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180023980`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180023980`
- `ntdll!RtlNtStatusToDosError` at `0x1800239da`
- `ntdll!RtlNtStatusToDosError` at `0x1800239da`

## pseudocode

```c
ULONG __fastcall LoadParameters(__int64 a1)
{
  _DWORD *v2; // rbx
  NTSTATUS RegistryValues; // edi

  v2 = LocalAlloc(0x40u, 0x70u);
  if ( v2 )
  {
    v2[2] = 16;
    *(_QWORD *)v2 = SetStickyParameter;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    v2[8] = 0;
    *((_QWORD *)v2 + 5) = 0;
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v2[16] = 0;
    *((_QWORD *)v2 + 9) = 0;
    RegistryValues = RtlQueryRegistryValuesEx(2147483649LL, a1, v2, a1, 0);
    LocalFree(v2);
    if ( RegistryValues >= 0 )
      return 0;
  }
  else
  {
    RegistryValues = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        (unsigned int)RegistryValues);
  }
  return RtlNtStatusToDosError(RegistryValues);
}

```

## disassembly

```asm
0x1800238f8  mov     [rsp+arg_0], rbx
0x1800238fd  push    rdi
0x1800238fe  sub     rsp, 30h
0x180023902  mov     edx, 70h ; 'p'; uBytes
0x180023907  mov     rdi, rcx
0x18002390a  lea     ecx, [rdx-30h]; uFlags
0x18002390d  call    cs:__imp_LocalAlloc
0x180023913  mov     rbx, rax
0x180023916  test    rax, rax
0x180023919  jz      short loc_180023999
0x18002391b  lea     rax, SetStickyParameter
0x180023922  mov     dword ptr [rbx+8], 10h
0x180023929  mov     r9, rdi
0x18002392c  mov     [rbx], rax
0x18002392f  mov     r8, rbx
0x180023932  mov     qword ptr [rbx+10h], 0
0x18002393a  mov     rdx, rdi
0x18002393d  mov     qword ptr [rbx+18h], 0
0x180023945  mov     ecx, 80000001h
0x18002394a  mov     dword ptr [rbx+20h], 0
0x180023951  mov     qword ptr [rbx+28h], 0
0x180023959  mov     dword ptr [rbx+30h], 0
0x180023960  mov     qword ptr [rbx+38h], 0
0x180023968  mov     dword ptr [rbx+40h], 0
0x18002396f  mov     qword ptr [rbx+48h], 0
0x180023977  mov     [rsp+38h+var_18], 0
0x180023980  call    cs:__imp_RtlQueryRegistryValuesEx
0x180023986  mov     rcx, rbx; hMem
0x180023989  mov     edi, eax
0x18002398b  call    cs:__imp_LocalFree
0x180023991  test    edi, edi
0x180023993  js      short loc_18002399E
0x180023995  xor     eax, eax
0x180023997  jmp     short loc_1800239E0
0x180023999  mov     edi, 0C000009Ah
0x18002399e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239a5  lea     rax, WPP_GLOBAL_Control
0x1800239ac  cmp     rcx, rax
0x1800239af  jz      short loc_1800239D8
0x1800239b1  test    dword ptr [rcx+1Ch], 100h
0x1800239b8  jz      short loc_1800239D8
0x1800239ba  cmp     byte ptr [rcx+19h], 1
0x1800239be  jb      short loc_1800239D8
0x1800239c0  mov     rcx, [rcx+10h]
0x1800239c4  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800239cb  mov     edx, 46h ; 'F'
0x1800239d0  mov     r9d, edi
0x1800239d3  call    WPP_SF_d
0x1800239d8  mov     ecx, edi; Status
0x1800239da  call    cs:__imp_RtlNtStatusToDosError
0x1800239e0  mov     rbx, [rsp+38h+arg_0]
0x1800239e5  add     rsp, 30h
0x1800239e9  pop     rdi
0x1800239ea  retn
```
