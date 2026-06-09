# TUNNEL_CloseRemoteTarget

- ea: `0x14008fd94`
- end: `0x14008ff20`
- name: `TUNNEL_CloseRemoteTarget`
- size: `396`
- prototype: `void __fastcall(_QWORD *, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14008fc38`
- `0x140090700`

## callees

- `0x1400024b8`
- `0x140041a30`
- `0x140045570`
- `0x14008fd94`

## import_xrefs

- `ntoskrnl!PoFxRemoveComponentRelation` at `0x14008fe2e`
- `ntoskrnl!PoFxRemoveComponentRelation` at `0x14008fe2e`

## pseudocode

```c
void __fastcall TUNNEL_CloseRemoteTarget(_QWORD *a1, int a2, int a3)
{
  __int64 v3; // rbx
  _QWORD *v5; // rdi
  char v6; // bp
  int v7; // eax
  int v8; // edx
  bool v9; // zf
  __int64 v10; // rdx
  __int64 v11; // [rsp+28h] [rbp-40h]

  v3 = a1[1];
  if ( v3 )
  {
    v5 = (_QWORD *)(v3 + 32);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = *(_QWORD *)(v3 + 8);
      WPP_RECORDER_SF_qqq(*(_QWORD *)(*a1 + 2536LL), a2, a3, 33);
    }
    v6 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 16),
      0);
    if ( *(_BYTE *)(v3 + 44) == 1 )
    {
      v7 = PoFxRemoveComponentRelation(*(_QWORD *)(*a1 + 2624LL), 0, *v5, &GUID_NULL);
      if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v11) = v7;
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*a1 + 2536LL),
          v8,
          3,
          34,
          (__int64)WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids,
          v11);
      }
      *(_BYTE *)(v3 + 44) = 0;
    }
    v9 = *(_DWORD *)(v3 + 24) == 3;
    *v5 = 0;
    if ( !v9 )
    {
      v6 = 1;
      *(_DWORD *)(v3 + 24) = 3;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 16));
    if ( v6 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1360))(
        WdfDriverGlobals,
        *(_QWORD *)(v3 + 8));
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
        WdfDriverGlobals,
        *(_QWORD *)(v3 + 16),
        0);
      v10 = *(_QWORD *)(v3 + 16);
      *(_DWORD *)(v3 + 24) = 4;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2512))(WdfDriverGlobals, v10);
    }
  }
}

```

## disassembly

```asm
0x14008fd94  push    rbx
0x14008fd96  push    rbp
0x14008fd97  push    rsi
0x14008fd98  push    rdi
0x14008fd99  push    r15
0x14008fd9b  sub     rsp, 40h
0x14008fd9f  mov     rbx, [rcx+8]
0x14008fda3  mov     rsi, rcx
0x14008fda6  test    rbx, rbx
0x14008fda9  jz      loc_14008FF14
0x14008fdaf  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008fdb6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008fdbd  lea     rdi, [rbx+20h]
0x14008fdc1  jz      short loc_14008FDEE
0x14008fdc3  mov     rax, [rdi]
0x14008fdc6  mov     r9d, 21h ; '!'
0x14008fdcc  mov     rcx, [rcx]
0x14008fdcf  mov     [rsp+68h+var_30], rbx
0x14008fdd4  mov     [rsp+68h+var_38], rax
0x14008fdd9  mov     rax, [rbx+8]
0x14008fddd  mov     rcx, [rcx+9E8h]
0x14008fde4  mov     [rsp+68h+var_40], rax
0x14008fde9  call    WPP_RECORDER_SF_qqq
0x14008fdee  mov     rax, cs:WdfFunctions_01015
0x14008fdf5  xor     r8d, r8d
0x14008fdf8  mov     rdx, [rbx+10h]
0x14008fdfc  xor     bpl, bpl
0x14008fdff  mov     rcx, cs:WdfDriverGlobals
0x14008fe06  mov     rax, [rax+9C8h]
0x14008fe0d  call    _guard_dispatch_icall
0x14008fe12  cmp     byte ptr [rbx+2Ch], 1
0x14008fe16  jnz     short loc_14008FE76
0x14008fe18  mov     rcx, [rsi]
0x14008fe1b  lea     r9, GUID_NULL
0x14008fe22  mov     r8, [rdi]
0x14008fe25  xor     edx, edx
0x14008fe27  mov     rcx, [rcx+0A40h]
0x14008fe2e  call    cs:__imp_PoFxRemoveComponentRelation
0x14008fe35  nop     dword ptr [rax+rax+00h]
0x14008fe3a  test    eax, eax
0x14008fe3c  jns     short loc_14008FE72
0x14008fe3e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14008fe45  jz      short loc_14008FE72
0x14008fe47  mov     rcx, [rsi]
0x14008fe4a  mov     r9d, 22h ; '"'
0x14008fe50  mov     dword ptr [rsp+68h+var_40], eax
0x14008fe54  mov     dl, 2
0x14008fe56  lea     rax, WPP_16d83da310273e0510a3edcc6c2bc223_Traceguids
0x14008fe5d  mov     [rsp+68h+var_48], rax
0x14008fe62  mov     rcx, [rcx+9E8h]
0x14008fe69  lea     r8d, [r9-1Fh]
0x14008fe6d  call    WPP_RECORDER_SF_d
0x14008fe72  mov     [rbx+2Ch], bpl
0x14008fe76  cmp     dword ptr [rbx+18h], 3
0x14008fe7a  mov     qword ptr [rdi], 0
0x14008fe81  jz      short loc_14008FE8D
0x14008fe83  mov     bpl, 1
0x14008fe86  mov     dword ptr [rbx+18h], 3
0x14008fe8d  mov     rax, cs:WdfFunctions_01015
0x14008fe94  mov     rdx, [rbx+10h]
0x14008fe98  mov     rcx, cs:WdfDriverGlobals
0x14008fe9f  mov     rax, [rax+9D0h]
0x14008fea6  call    _guard_dispatch_icall
0x14008feab  test    bpl, bpl
0x14008feae  jz      short loc_14008FF14
0x14008feb0  mov     rax, cs:WdfFunctions_01015
0x14008feb7  mov     rdx, [rbx+8]
0x14008febb  mov     rcx, cs:WdfDriverGlobals
0x14008fec2  mov     rax, [rax+550h]
0x14008fec9  call    _guard_dispatch_icall
0x14008fece  mov     rax, cs:WdfFunctions_01015
0x14008fed5  xor     r8d, r8d
0x14008fed8  mov     rdx, [rbx+10h]
0x14008fedc  mov     rcx, cs:WdfDriverGlobals
0x14008fee3  mov     rax, [rax+9C8h]
0x14008feea  call    _guard_dispatch_icall
0x14008feef  mov     rdx, [rbx+10h]
0x14008fef3  mov     dword ptr [rbx+18h], 4
0x14008fefa  mov     rax, cs:WdfFunctions_01015
0x14008ff01  mov     rcx, cs:WdfDriverGlobals
0x14008ff08  mov     rax, [rax+9D0h]
0x14008ff0f  call    _guard_dispatch_icall
0x14008ff14  add     rsp, 40h
0x14008ff18  pop     r15
0x14008ff1a  pop     rdi
0x14008ff1b  pop     rsi
0x14008ff1c  pop     rbp
0x14008ff1d  pop     rbx
0x14008ff1e  retn
```
