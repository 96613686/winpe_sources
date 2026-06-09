# InstanceCreate

- ea: `0x140027e00`
- end: `0x140027f82`
- name: `InstanceCreate`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140017190`
- `0x140027e00`
- `0x14002f200`
- `0x14002f3dc`

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
0x140027e00  push    rbx
0x140027e02  push    rbp
0x140027e03  push    rsi
0x140027e04  push    rdi
0x140027e05  sub     rsp, 48h
0x140027e09  xor     eax, eax
0x140027e0b  xorps   xmm0, xmm0
0x140027e0e  mov     [rsp+68h+var_38], rax
0x140027e13  mov     rbp, rdx
0x140027e16  mov     rax, cs:WdfFunctions_01033
0x140027e1d  mov     rsi, r8
0x140027e20  mov     r8, cs:off_14001C160
0x140027e27  mov     rdi, rcx
0x140027e2a  movups  [rsp+68h+var_48], xmm0
0x140027e2f  mov     rdx, rcx
0x140027e32  mov     rcx, cs:WdfDriverGlobals
0x140027e39  mov     rax, [rax+650h]
0x140027e40  call    _guard_dispatch_icall
0x140027e45  mov     rbx, rax
0x140027e48  movzx   eax, word ptr [rax+98h]
0x140027e4f  test    al, 10h
0x140027e51  jz      loc_140027F35
0x140027e57  bt      eax, 0Dh
0x140027e5b  jnb     short loc_140027E83
0x140027e5d  mov     rcx, cs:WdfFunctions_01033
0x140027e64  mov     rdx, rsi
0x140027e67  mov     rax, [rcx+460h]
0x140027e6e  mov     rcx, cs:WdfDriverGlobals
0x140027e75  call    _guard_dispatch_icall
0x140027e7a  mov     [rax+18h], rdi
0x140027e7e  jmp     loc_140027F35
0x140027e83  cmp     dword ptr [rbx+3Ch], 0
0x140027e87  jz      short loc_140027E94
0x140027e89  mov     r8d, 0C000011Fh
0x140027e8f  jmp     loc_140027F5B
0x140027e94  mov     rax, cs:WdfFunctions_01033
0x140027e9b  mov     rdx, rsi
0x140027e9e  mov     rcx, cs:WdfDriverGlobals
0x140027ea5  mov     rax, [rax+448h]
0x140027eac  call    _guard_dispatch_icall
0x140027eb1  lea     rdx, [rsp+68h+var_48]
0x140027eb6  mov     rcx, rax
0x140027eb9  call    PipeParseFilename
0x140027ebe  mov     r8d, eax
0x140027ec1  test    eax, eax
0x140027ec3  js      loc_140027F5B
0x140027ec9  mov     rax, cs:WdfFunctions_01033
0x140027ed0  mov     rdx, rdi
0x140027ed3  mov     rcx, cs:WdfDriverGlobals
0x140027eda  mov     rax, [rax+0F8h]
0x140027ee1  call    _guard_dispatch_icall
0x140027ee6  mov     rcx, [rbx+128h]; SpinLock
0x140027eed  lea     r9, [rsp+68h+var_48]
0x140027ef2  xor     r8d, r8d
0x140027ef5  mov     rdx, rax
0x140027ef8  call    PipeAccept
0x140027efd  mov     r8d, eax
0x140027f00  test    eax, eax
0x140027f02  jns     short loc_140027F13
0x140027f04  cmp     eax, 0C000000Dh
0x140027f09  jz      short loc_140027F5B
0x140027f0b  mov     r8d, 0C00000ADh
0x140027f11  jmp     short loc_140027F5B
0x140027f13  mov     rax, cs:WdfFunctions_01033
0x140027f1a  mov     rdx, rsi
0x140027f1d  mov     rcx, cs:WdfDriverGlobals
0x140027f24  mov     rax, [rax+460h]
0x140027f2b  call    _guard_dispatch_icall
0x140027f30  bts     dword ptr [rax+50h], 7
0x140027f35  mov     rax, cs:WdfFunctions_01033
0x140027f3c  xor     r8d, r8d
0x140027f3f  mov     rcx, cs:WdfDriverGlobals
0x140027f46  mov     rdx, rdi
0x140027f49  mov     rax, [rax+260h]
0x140027f50  call    _guard_dispatch_icall
0x140027f55  inc     dword ptr [rbx+3Ch]
0x140027f58  xor     r8d, r8d
0x140027f5b  mov     rax, cs:WdfFunctions_01033
0x140027f62  mov     rdx, rbp
0x140027f65  mov     rcx, cs:WdfDriverGlobals
0x140027f6c  mov     rax, [rax+838h]
0x140027f73  call    _guard_dispatch_icall
0x140027f78  add     rsp, 48h
0x140027f7c  pop     rdi
0x140027f7d  pop     rsi
0x140027f7e  pop     rbp
0x140027f7f  pop     rbx
0x140027f80  retn
```
