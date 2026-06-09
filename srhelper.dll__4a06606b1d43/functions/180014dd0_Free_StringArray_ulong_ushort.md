# Free_StringArray(ulong *,ushort * * *)

- ea: `0x180014dd0`
- end: `0x180014e28`
- name: `?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z`
- size: `88`
- prototype: `void __fastcall(unsigned int *, LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000ab80`
- `0x18000af70`
- `0x18000b3b0`

## callees

- `0x180014dd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180014df2`
- `ole32!CoTaskMemFree` at `0x180014e0c`
- `ole32!CoTaskMemFree` at `0x180014df2`
- `ole32!CoTaskMemFree` at `0x180014e0c`

## pseudocode

```c
void __fastcall Free_StringArray(unsigned int *a1, LPVOID *a2)
{
  __int64 i; // rbp

  if ( *a2 )
  {
    for ( i = 0; (unsigned int)i < *a1; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree(*((LPVOID *)*a2 + i));
      *((_QWORD *)*a2 + i) = 0;
    }
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x180014dd0  push    rbx
0x180014dd2  push    rbp
0x180014dd3  push    rsi
0x180014dd4  push    rdi
0x180014dd5  sub     rsp, 28h
0x180014dd9  cmp     qword ptr [rdx], 0
0x180014ddd  mov     rdi, rdx
0x180014de0  mov     rsi, rcx
0x180014de3  jz      short loc_180014E19
0x180014de5  xor     ebp, ebp
0x180014de7  cmp     [rcx], ebp
0x180014de9  jbe     short loc_180014E09
0x180014deb  mov     rcx, [rdi]
0x180014dee  mov     rcx, [rcx+rbp*8]; pv
0x180014df2  call    cs:__imp_CoTaskMemFree
0x180014df8  mov     rax, [rdi]
0x180014dfb  mov     qword ptr [rax+rbp*8], 0
0x180014e03  inc     ebp
0x180014e05  cmp     ebp, [rsi]
0x180014e07  jb      short loc_180014DEB
0x180014e09  mov     rcx, [rdi]; pv
0x180014e0c  call    cs:__imp_CoTaskMemFree
0x180014e12  mov     qword ptr [rdi], 0
0x180014e19  mov     dword ptr [rsi], 0
0x180014e1f  add     rsp, 28h
0x180014e23  pop     rdi
0x180014e24  pop     rsi
0x180014e25  pop     rbp
0x180014e26  pop     rbx
0x180014e27  retn
```
