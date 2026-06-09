# HUBREG_UpdateUxdSettings

- ea: `0x14008ade0`
- end: `0x14008af92`
- name: `HUBREG_UpdateUxdSettings`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007ab24`
- `0x14007ea48`

## callees

- `0x140045530`
- `0x140045570`
- `0x140045940`
- `0x1400878b0`
- `0x14008928c`
- `0x140089418`
- `0x14008ade0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14008af4e`
- `ntoskrnl!RtlCompareMemory` at `0x14008af4e`

## pseudocode

```c
__int64 __fastcall HUBREG_UpdateUxdSettings(__int64 a1, __int64 a2, _BYTE *a3)
{
  int v6; // eax
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int64 v10; // rsi
  __int128 v11; // xmm1
  int v12; // eax
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  _OWORD Source1[5]; // [rsp+20h] [rbp-79h] BYREF
  _OWORD Source2[5]; // [rsp+70h] [rbp-29h] BYREF

  memset(Source1, 0, 0x44u);
  memset(Source2, 0, 0x44u);
  if ( a3 )
    *a3 = 0;
  _InterlockedAnd((volatile signed __int32 *)(a2 + 1640), 0xFFFFFFFE);
  v6 = *(_DWORD *)(a2 + 1736);
  v7 = *(_OWORD *)(a2 + 1688);
  Source2[0] = *(_OWORD *)(a2 + 1672);
  v8 = *(_OWORD *)(a2 + 1704);
  LODWORD(Source2[4]) = v6;
  Source2[1] = v7;
  v9 = *(_OWORD *)(a2 + 1720);
  Source2[2] = v8;
  Source2[3] = v9;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          WdfDriverGlobals->Driver,
          off_14006B2C0);
  if ( (int)HUBREG_QueryGlobalUxdSettings(v10) >= 0 && (*(_DWORD *)(v10 + 4) & 0x810) == 0x800 )
  {
    if ( (int)HUBREG_QueryUxdPortKey(a1, *(unsigned __int16 *)(*(_QWORD *)(a2 + 8) + 200LL), Source1) >= 0
      || (memset(Source1, 0, 0x44u), (int)HUBREG_QueryUxdDeviceKey(a2, (__int64)Source1) >= 0) )
    {
      _InterlockedOr((volatile signed __int32 *)(a2 + 1640), 1u);
      _InterlockedOr((volatile signed __int32 *)(a2 + 1648), 4u);
    }
    v11 = Source1[1];
    v12 = Source1[4];
    *(_OWORD *)(a2 + 1672) = Source1[0];
    v13 = Source1[2];
    *(_OWORD *)(a2 + 1688) = v11;
    v14 = Source1[3];
    *(_OWORD *)(a2 + 1704) = v13;
    *(_OWORD *)(a2 + 1720) = v14;
    *(_DWORD *)(a2 + 1736) = v12;
    if ( a3 && RtlCompareMemory(Source1, Source2, 0x44u) != 68 && (*(_DWORD *)(a2 + 1640) & 2) == 0 )
      *a3 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14008ade0  mov     [rsp-8+arg_18], rbx
0x14008ade5  push    rbp
0x14008ade6  push    rsi
0x14008ade7  push    rdi
0x14008ade8  push    r14
0x14008adea  push    r15
0x14008adec  lea     rbp, [rsp-37h]
0x14008adf1  sub     rsp, 0D0h
0x14008adf8  mov     rax, cs:__security_cookie
0x14008adff  xor     rax, rsp
0x14008ae02  mov     [rbp+57h+var_30], rax
0x14008ae06  mov     rdi, r8
0x14008ae09  mov     rbx, rdx
0x14008ae0c  mov     r14, rcx
0x14008ae0f  mov     r15d, 44h ; 'D'
0x14008ae15  mov     r8d, r15d; Size
0x14008ae18  lea     rcx, [rbp+57h+Source1]; void *
0x14008ae1c  xor     edx, edx; Val
0x14008ae1e  call    memset
0x14008ae23  mov     r8d, r15d; Size
0x14008ae26  lea     rcx, [rbp+57h+Source2]; void *
0x14008ae2a  xor     edx, edx; Val
0x14008ae2c  call    memset
0x14008ae31  test    rdi, rdi
0x14008ae34  jz      short loc_14008AE39
0x14008ae36  mov     byte ptr [rdi], 0
0x14008ae39  lock and dword ptr [rbx+668h], 0FFFFFFFEh
0x14008ae41  movups  xmm0, xmmword ptr [rbx+688h]
0x14008ae48  mov     eax, [rbx+6C8h]
0x14008ae4e  movups  xmm1, xmmword ptr [rbx+698h]
0x14008ae55  mov     rcx, cs:WdfDriverGlobals
0x14008ae5c  mov     r8, cs:off_14006B2C0
0x14008ae63  movaps  [rbp+57h+Source2], xmm0
0x14008ae67  movups  xmm0, xmmword ptr [rbx+6A8h]
0x14008ae6e  mov     [rbp+57h+var_40], eax
0x14008ae71  mov     rax, cs:WdfFunctions_01015
0x14008ae78  movaps  [rbp+57h+var_70], xmm1
0x14008ae7c  movups  xmm1, xmmword ptr [rbx+6B8h]
0x14008ae83  movaps  [rbp+57h+var_60], xmm0
0x14008ae87  movaps  [rbp+57h+var_50], xmm1
0x14008ae8b  mov     rax, [rax+650h]
0x14008ae92  mov     rdx, [rcx]
0x14008ae95  call    _guard_dispatch_icall
0x14008ae9a  mov     rcx, rax
0x14008ae9d  mov     rsi, rax
0x14008aea0  call    HUBREG_QueryGlobalUxdSettings
0x14008aea5  test    eax, eax
0x14008aea7  js      loc_14008AF6C
0x14008aead  mov     eax, [rsi+4]
0x14008aeb0  and     eax, 810h
0x14008aeb5  cmp     eax, 800h
0x14008aeba  jnz     loc_14008AF6C
0x14008aec0  mov     rax, [rbx+8]
0x14008aec4  lea     r8, [rbp+57h+Source1]
0x14008aec8  mov     rcx, r14
0x14008aecb  movzx   edx, word ptr [rax+0C8h]
0x14008aed2  call    HUBREG_QueryUxdPortKey
0x14008aed7  test    eax, eax
0x14008aed9  jns     short loc_14008AEF9
0x14008aedb  mov     r8, r15; Size
0x14008aede  lea     rcx, [rbp+57h+Source1]; void *
0x14008aee2  xor     edx, edx; Val
0x14008aee4  call    memset
0x14008aee9  lea     rdx, [rbp+57h+Source1]
0x14008aeed  mov     rcx, rbx
0x14008aef0  call    HUBREG_QueryUxdDeviceKey
0x14008aef5  test    eax, eax
0x14008aef7  js      short loc_14008AF09
0x14008aef9  lock or dword ptr [rbx+668h], 1
0x14008af01  lock or dword ptr [rbx+670h], 4
0x14008af09  movaps  xmm0, [rbp+57h+Source1]
0x14008af0d  movaps  xmm1, [rbp+57h+var_C0]
0x14008af11  mov     eax, [rbp+57h+var_90]
0x14008af14  movups  xmmword ptr [rbx+688h], xmm0
0x14008af1b  movaps  xmm0, [rbp+57h+var_B0]
0x14008af1f  movups  xmmword ptr [rbx+698h], xmm1
0x14008af26  movaps  xmm1, [rbp+57h+var_A0]
0x14008af2a  movups  xmmword ptr [rbx+6A8h], xmm0
0x14008af31  movups  xmmword ptr [rbx+6B8h], xmm1
0x14008af38  mov     [rbx+6C8h], eax
0x14008af3e  test    rdi, rdi
0x14008af41  jz      short loc_14008AF6C
0x14008af43  mov     r8, r15; Length
0x14008af46  lea     rdx, [rbp+57h+Source2]; Source2
0x14008af4a  lea     rcx, [rbp+57h+Source1]; Source1
0x14008af4e  call    cs:__imp_RtlCompareMemory
0x14008af55  nop     dword ptr [rax+rax+00h]
0x14008af5a  cmp     rax, r15
0x14008af5d  jz      short loc_14008AF6C
0x14008af5f  mov     eax, [rbx+668h]
0x14008af65  test    al, 2
0x14008af67  jnz     short loc_14008AF6C
0x14008af69  mov     byte ptr [rdi], 1
0x14008af6c  xor     eax, eax
0x14008af6e  mov     rcx, [rbp+57h+var_30]
0x14008af72  xor     rcx, rsp; StackCookie
0x14008af75  call    __security_check_cookie
0x14008af7a  mov     rbx, [rsp+0F0h+arg_18]
0x14008af82  add     rsp, 0D0h
0x14008af89  pop     r15
0x14008af8b  pop     r14
0x14008af8d  pop     rdi
0x14008af8e  pop     rsi
0x14008af8f  pop     rbp
0x14008af90  retn
```
