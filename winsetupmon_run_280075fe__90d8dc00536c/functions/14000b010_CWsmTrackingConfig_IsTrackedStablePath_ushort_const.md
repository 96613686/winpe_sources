# CWsmTrackingConfig::IsTrackedStablePath(ushort const *)

- ea: `0x14000b010`
- end: `0x14000b05e`
- name: `?IsTrackedStablePath@CWsmTrackingConfig@@UEBAEPEBG@Z`
- size: `78`
- prototype: `unsigned __int8(CWsmTrackingConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000b010`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14000b039`
- `ntoskrnl!_wcsicmp` at `0x14000b039`

## pseudocode

```c
char __fastcall CWsmTrackingConfig::IsTrackedStablePath(CWsmTrackingConfig *this, const unsigned __int16 *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  char v5; // bl

  v2 = *((_QWORD *)this + 5);
  v3 = 0;
  if ( !*(_DWORD *)(v2 + 104) )
    return 0;
  v5 = 1;
  while ( _wcsicmp(*(const wchar_t **)(*(_QWORD *)(v2 + 112) + 24 * v3), a2) )
  {
    v3 = (unsigned int)(v3 + 1);
    if ( (unsigned int)v3 >= *(_DWORD *)(v2 + 104) )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x14000b010  push    rbx
0x14000b012  push    rbp
0x14000b013  push    rsi
0x14000b014  push    rdi
0x14000b015  sub     rsp, 28h
0x14000b019  mov     rsi, [rcx+28h]
0x14000b01d  xor     edi, edi
0x14000b01f  mov     rbp, rdx
0x14000b022  cmp     [rsi+68h], edi
0x14000b025  jbe     short loc_14000B050
0x14000b027  lea     ebx, [rdi+1]
0x14000b02a  mov     rcx, [rsi+70h]
0x14000b02e  lea     r8, [rdi+rdi*2]
0x14000b032  mov     rdx, rbp; Str2
0x14000b035  mov     rcx, [rcx+r8*8]; Str1
0x14000b039  call    cs:__imp__wcsicmp
0x14000b040  nop     dword ptr [rax+rax+00h]
0x14000b045  test    eax, eax
0x14000b047  jz      short loc_14000B052
0x14000b049  add     edi, ebx
0x14000b04b  cmp     edi, [rsi+68h]
0x14000b04e  jb      short loc_14000B02A
0x14000b050  xor     bl, bl
0x14000b052  mov     al, bl
0x14000b054  add     rsp, 28h
0x14000b058  pop     rdi
0x14000b059  pop     rsi
0x14000b05a  pop     rbp
0x14000b05b  pop     rbx
0x14000b05c  retn
```
