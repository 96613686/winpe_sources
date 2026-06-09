# InstanceCreate

- ea: `0x140027db0`
- end: `0x140027f32`
- name: `InstanceCreate`
- size: `386`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140017190`
- `0x140027db0`
- `0x14002f1b0`
- `0x14002f38c`

## pseudocode

```c
__int64 __fastcall InstanceCreate(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  __int128 v13; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-38h]

  v14 = 0;
  v13 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14001C160);
  if ( (*(_WORD *)(v6 + 152) & 0x10) == 0 )
    goto LABEL_11;
  if ( (*(_WORD *)(v6 + 152) & 0x2000) != 0 )
  {
    *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 1120))(
                  WdfDriverGlobals,
                  a3)
              + 24) = a1;
LABEL_11:
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 608))(WdfDriverGlobals, a1, 0);
    ++*(_DWORD *)(v6 + 60);
    v7 = 0;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             a2,
             v7);
  }
  if ( *(_DWORD *)(v6 + 60) )
  {
    v7 = 3221225759LL;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 1096))(WdfDriverGlobals, a3);
    v9 = PipeParseFilename(v8, &v13);
    v7 = (unsigned int)v9;
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 248))(
        WdfDriverGlobals,
        a1,
        (unsigned int)v9);
      v10 = PipeAccept(*(PKSPIN_LOCK *)(v6 + 296));
      v7 = (unsigned int)v10;
      if ( v10 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 1120))(
                WdfDriverGlobals,
                a3,
                (unsigned int)v10);
        *(_DWORD *)(v11 + 80) |= 0x80u;
        goto LABEL_11;
      }
      if ( v10 != -1073741811 )
        v7 = 3221225645LL;
    }
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v7);
}

```

## disassembly

```asm
0x140027db0  push    rbx
0x140027db2  push    rbp
0x140027db3  push    rsi
0x140027db4  push    rdi
0x140027db5  sub     rsp, 48h
0x140027db9  xor     eax, eax
0x140027dbb  xorps   xmm0, xmm0
0x140027dbe  mov     [rsp+68h+var_38], rax
0x140027dc3  mov     rbp, rdx
0x140027dc6  mov     rax, cs:WdfFunctions_01033
0x140027dcd  mov     rsi, r8
0x140027dd0  mov     r8, cs:off_14001C160
0x140027dd7  mov     rdi, rcx
0x140027dda  movups  [rsp+68h+var_48], xmm0
0x140027ddf  mov     rdx, rcx
0x140027de2  mov     rcx, cs:WdfDriverGlobals
0x140027de9  mov     rax, [rax+650h]
0x140027df0  call    _guard_dispatch_icall
0x140027df5  mov     rbx, rax
0x140027df8  movzx   eax, word ptr [rax+98h]
0x140027dff  test    al, 10h
0x140027e01  jz      loc_140027EE5
0x140027e07  bt      eax, 0Dh
0x140027e0b  jnb     short loc_140027E33
0x140027e0d  mov     rcx, cs:WdfFunctions_01033
0x140027e14  mov     rdx, rsi
0x140027e17  mov     rax, [rcx+460h]
0x140027e1e  mov     rcx, cs:WdfDriverGlobals
0x140027e25  call    _guard_dispatch_icall
0x140027e2a  mov     [rax+18h], rdi
0x140027e2e  jmp     loc_140027EE5
0x140027e33  cmp     dword ptr [rbx+3Ch], 0
0x140027e37  jz      short loc_140027E44
0x140027e39  mov     r8d, 0C000011Fh
0x140027e3f  jmp     loc_140027F0B
0x140027e44  mov     rax, cs:WdfFunctions_01033
0x140027e4b  mov     rdx, rsi
0x140027e4e  mov     rcx, cs:WdfDriverGlobals
0x140027e55  mov     rax, [rax+448h]
0x140027e5c  call    _guard_dispatch_icall
0x140027e61  lea     rdx, [rsp+68h+var_48]
0x140027e66  mov     rcx, rax
0x140027e69  call    PipeParseFilename
0x140027e6e  mov     r8d, eax
0x140027e71  test    eax, eax
0x140027e73  js      loc_140027F0B
0x140027e79  mov     rax, cs:WdfFunctions_01033
0x140027e80  mov     rdx, rdi
0x140027e83  mov     rcx, cs:WdfDriverGlobals
0x140027e8a  mov     rax, [rax+0F8h]
0x140027e91  call    _guard_dispatch_icall
0x140027e96  mov     rcx, [rbx+128h]; SpinLock
0x140027e9d  lea     r9, [rsp+68h+var_48]
0x140027ea2  xor     r8d, r8d
0x140027ea5  mov     rdx, rax
0x140027ea8  call    PipeAccept
0x140027ead  mov     r8d, eax
0x140027eb0  test    eax, eax
0x140027eb2  jns     short loc_140027EC3
0x140027eb4  cmp     eax, 0C000000Dh
0x140027eb9  jz      short loc_140027F0B
0x140027ebb  mov     r8d, 0C00000ADh
0x140027ec1  jmp     short loc_140027F0B
0x140027ec3  mov     rax, cs:WdfFunctions_01033
0x140027eca  mov     rdx, rsi
0x140027ecd  mov     rcx, cs:WdfDriverGlobals
0x140027ed4  mov     rax, [rax+460h]
0x140027edb  call    _guard_dispatch_icall
0x140027ee0  bts     dword ptr [rax+50h], 7
0x140027ee5  mov     rax, cs:WdfFunctions_01033
0x140027eec  xor     r8d, r8d
0x140027eef  mov     rcx, cs:WdfDriverGlobals
0x140027ef6  mov     rdx, rdi
0x140027ef9  mov     rax, [rax+260h]
0x140027f00  call    _guard_dispatch_icall
0x140027f05  inc     dword ptr [rbx+3Ch]
0x140027f08  xor     r8d, r8d
0x140027f0b  mov     rax, cs:WdfFunctions_01033
0x140027f12  mov     rdx, rbp
0x140027f15  mov     rcx, cs:WdfDriverGlobals
0x140027f1c  mov     rax, [rax+838h]
0x140027f23  call    _guard_dispatch_icall
0x140027f28  add     rsp, 48h
0x140027f2c  pop     rdi
0x140027f2d  pop     rsi
0x140027f2e  pop     rbp
0x140027f2f  pop     rbx
0x140027f30  retn
```
