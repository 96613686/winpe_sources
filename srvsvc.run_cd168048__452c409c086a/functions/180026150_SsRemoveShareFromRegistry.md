# SsRemoveShareFromRegistry

- ea: `0x180026150`
- end: `0x180026218`
- name: `SsRemoveShareFromRegistry`
- size: `200`
- prototype: `__int64 __fastcall(PCWSTR ValueName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a890`
- `0x18002abf0`

## callees

- `0x180026150`
- `0x1800268d8`

## import_xrefs

- `ntdll!RtlDeleteRegistryValue` at `0x18002616b`
- `ntdll!RtlDeleteRegistryValue` at `0x1800261be`
- `ntdll!RtlDeleteRegistryValue` at `0x18002616b`
- `ntdll!RtlDeleteRegistryValue` at `0x1800261be`
- `ntdll!RtlNtStatusToDosError` at `0x180026204`
- `ntdll!RtlNtStatusToDosError` at `0x180026204`

## pseudocode

```c
__int64 __fastcall SsRemoveShareFromRegistry(PCWSTR ValueName)
{
  unsigned int v2; // edi
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx

  v2 = 0;
  v3 = RtlDeleteRegistryValue(0, &word_18005DFC4, ValueName);
  if ( v3 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
      v3,
      (__int64)ValueName);
  }
  v4 = RtlDeleteRegistryValue(0, &word_18005DDBC, ValueName);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        v4,
        (__int64)ValueName);
    }
    return RtlNtStatusToDosError(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x180026150  push    rbx
0x180026152  push    rsi
0x180026153  push    rdi
0x180026154  push    r14
0x180026156  sub     rsp, 38h
0x18002615a  mov     rsi, rcx
0x18002615d  lea     rdx, word_18005DFC4; Path
0x180026164  mov     r8, rcx; ValueName
0x180026167  xor     edi, edi
0x180026169  xor     ecx, ecx; RelativeTo
0x18002616b  call    cs:__imp_RtlDeleteRegistryValue
0x180026171  lea     r14, WPP_GLOBAL_Control
0x180026178  test    eax, eax
0x18002617a  jns     short loc_1800261B2
0x18002617c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026183  cmp     rcx, r14
0x180026186  jz      short loc_1800261B2
0x180026188  test    dword ptr [rcx+1Ch], 100h
0x18002618f  jz      short loc_1800261B2
0x180026191  cmp     byte ptr [rcx+19h], 1
0x180026195  jb      short loc_1800261B2
0x180026197  mov     rcx, [rcx+10h]
0x18002619b  lea     edx, [rdi+2Dh]
0x18002619e  mov     r9d, eax
0x1800261a1  mov     [rsp+58h+var_38], rsi
0x1800261a6  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800261ad  call    WPP_SF_dS
0x1800261b2  mov     r8, rsi; ValueName
0x1800261b5  lea     rdx, word_18005DDBC; Path
0x1800261bc  xor     ecx, ecx; RelativeTo
0x1800261be  call    cs:__imp_RtlDeleteRegistryValue
0x1800261c4  mov     ebx, eax
0x1800261c6  test    eax, eax
0x1800261c8  jns     short loc_18002620C
0x1800261ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261d1  cmp     rcx, r14
0x1800261d4  jz      short loc_180026202
0x1800261d6  test    dword ptr [rcx+1Ch], 100h
0x1800261dd  jz      short loc_180026202
0x1800261df  cmp     byte ptr [rcx+19h], 1
0x1800261e3  jb      short loc_180026202
0x1800261e5  mov     rcx, [rcx+10h]
0x1800261e9  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800261f0  mov     edx, 2Eh ; '.'
0x1800261f5  mov     [rsp+58h+var_38], rsi
0x1800261fa  mov     r9d, eax
0x1800261fd  call    WPP_SF_dS
0x180026202  mov     ecx, ebx; Status
0x180026204  call    cs:__imp_RtlNtStatusToDosError
0x18002620a  mov     edi, eax
0x18002620c  mov     eax, edi
0x18002620e  add     rsp, 38h
0x180026212  pop     r14
0x180026214  pop     rdi
0x180026215  pop     rsi
0x180026216  pop     rbx
0x180026217  retn
```
