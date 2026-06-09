# SspirLogonSystemManagedAdmin

- ea: `0x180002ca0`
- end: `0x180002d11`
- name: `SspirLogonSystemManagedAdmin`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002ca0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirLogonSystemManagedAdmin(__int64 a1, __int128 *a2, __int64 a3, _QWORD *a4)
{
  __int64 (__fastcall *v5)(__int64, __int128 *, __int64, __int64 *); // rax
  __int64 result; // rax
  unsigned int v7; // ecx
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+38h] [rbp-20h] BYREF

  v8 = 0;
  if ( gLsapSspiExtension
    && (v5 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64 *))(gLsapSspiExtension + 136)) != 0 )
  {
    if ( a2 && a4 )
    {
      v9 = *a2;
      result = v5(a1, &v9, a3, &v8);
      v7 = result;
      if ( (int)result < 0 )
        return result;
      *a4 = v8;
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741637;
  }
  return v7;
}

```

## disassembly

```asm
0x180002ca0  push    rbx
0x180002ca2  sub     rsp, 50h
0x180002ca6  mov     rax, cs:gLsapSspiExtension
0x180002cad  mov     rbx, r9
0x180002cb0  mov     [rsp+58h+var_28], 0
0x180002cb9  test    rax, rax
0x180002cbc  jz      short loc_180002D03
0x180002cbe  mov     rax, [rax+88h]
0x180002cc5  test    rax, rax
0x180002cc8  jz      short loc_180002D03
0x180002cca  test    rdx, rdx
0x180002ccd  jz      short loc_180002CFC
0x180002ccf  test    rbx, rbx
0x180002cd2  jz      short loc_180002CFC
0x180002cd4  movups  xmm0, xmmword ptr [rdx]
0x180002cd7  lea     r9, [rsp+58h+var_28]
0x180002cdc  lea     rdx, [rsp+58h+var_20]
0x180002ce1  movdqu  [rsp+58h+var_20], xmm0
0x180002ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cec  mov     ecx, eax
0x180002cee  test    eax, eax
0x180002cf0  js      short loc_180002D0A
0x180002cf2  mov     rax, [rsp+58h+var_28]
0x180002cf7  mov     [rbx], rax
0x180002cfa  jmp     short loc_180002D08
0x180002cfc  mov     ecx, 0C000000Dh
0x180002d01  jmp     short loc_180002D08
0x180002d03  mov     ecx, 0C00000BBh
0x180002d08  mov     eax, ecx
0x180002d0a  add     rsp, 50h
0x180002d0e  pop     rbx
0x180002d0f  retn
```
