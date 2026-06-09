# WdsImgGroupSetSecurity

- ea: `0x180006cb0`
- end: `0x180006d59`
- name: `WdsImgGroupSetSecurity`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006714`
- `0x180006cb0`
- `0x18000dfdc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180006d0c`
- `KERNEL32!GetProcessHeap` at `0x180006d0c`
- `KERNEL32!HeapFree` at `0x180006d20`
- `KERNEL32!HeapFree` at `0x180006d20`

## pseudocode

```c
__int64 __fastcall WdsImgGroupSetSecurity(__int64 a1, const WCHAR *a2)
{
  unsigned int v3; // ebx
  WCHAR *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  void *v9; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 && *a2 && a1 )
  {
    if ( *(_DWORD *)(a1 + 16) == 2 )
    {
      v4 = *(WCHAR **)(a1 + 32);
      v12 = 0;
      v3 = pWdsImgSetSecurity(v4, a2, &v12);
      if ( (int)ElValidateHr_1(v3, v5, v6, 305) >= 0 )
      {
        v9 = *(void **)(a1 + 40);
        if ( v9 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v9);
        }
        *(_QWORD *)(a1 + 40) = v12;
      }
      ElValidateHr_1(v3, v7, v8, 855);
    }
    else
    {
      return (unsigned int)-1056833019;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180006cb0  mov     [rsp+arg_0], rbx
0x180006cb5  push    rbp
0x180006cb6  push    rsi
0x180006cb7  push    rdi
0x180006cb8  sub     rsp, 20h
0x180006cbc  xor     ebp, ebp
0x180006cbe  mov     rdi, rcx
0x180006cc1  test    rdx, rdx
0x180006cc4  jz      short loc_180006D44
0x180006cc6  cmp     [rdx], bp
0x180006cc9  jz      short loc_180006D44
0x180006ccb  test    rcx, rcx
0x180006cce  jz      short loc_180006D44
0x180006cd0  cmp     dword ptr [rcx+10h], 2
0x180006cd4  jz      short loc_180006CDD
0x180006cd6  mov     ebx, 0C1020205h
0x180006cdb  jmp     short loc_180006D49
0x180006cdd  mov     rcx, [rcx+20h]; lpFileName
0x180006ce1  lea     r8, [rsp+38h+arg_10]; unsigned __int16 **
0x180006ce6  mov     [rsp+38h+arg_10], rbp
0x180006ceb  call    ?pWdsImgSetSecurity@@YAJPEAG0PEAPEAG@Z; pWdsImgSetSecurity(ushort *,ushort *,ushort * *)
0x180006cf0  mov     r9d, 131h
0x180006cf6  mov     ecx, eax
0x180006cf8  mov     ebx, eax
0x180006cfa  call    ElValidateHr_1
0x180006cff  test    eax, eax
0x180006d01  js      short loc_180006D35
0x180006d03  mov     rsi, [rdi+28h]
0x180006d07  test    rsi, rsi
0x180006d0a  jz      short loc_180006D2C
0x180006d0c  call    cs:__imp_GetProcessHeap
0x180006d13  nop     dword ptr [rax+rax+00h]
0x180006d18  mov     r8, rsi; lpMem
0x180006d1b  xor     edx, edx; dwFlags
0x180006d1d  mov     rcx, rax; hHeap
0x180006d20  call    cs:__imp_HeapFree
0x180006d27  nop     dword ptr [rax+rax+00h]
0x180006d2c  mov     rax, [rsp+38h+arg_10]
0x180006d31  mov     [rdi+28h], rax
0x180006d35  mov     r9d, 357h
0x180006d3b  mov     ecx, ebx
0x180006d3d  call    ElValidateHr_1
0x180006d42  jmp     short loc_180006D49
0x180006d44  mov     ebx, 80070057h
0x180006d49  mov     eax, ebx
0x180006d4b  mov     rbx, [rsp+38h+arg_0]
0x180006d50  add     rsp, 20h
0x180006d54  pop     rdi
0x180006d55  pop     rsi
0x180006d56  pop     rbp
0x180006d57  retn
```
