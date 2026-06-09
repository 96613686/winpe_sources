# UmpoInternalGetSuspensionPowerMode

- ea: `0x18001337c`
- end: `0x18001340b`
- name: `UmpoInternalGetSuspensionPowerMode`
- size: `143`
- prototype: `__int64 __fastcall(int, __int64, GUID *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012a0`
- `0x180001580`
- `0x1800027d4`
- `0x180002bc0`
- `0x18000e6e4`
- `0x18000f4f4`

## callees

- `0x180002d8c`
- `0x180010070`
- `0x18001337c`

## pseudocode

```c
__int64 __fastcall UmpoInternalGetSuspensionPowerMode(int a1, __int64 a2, GUID *a3)
{
  char v3; // si
  __int64 result; // rax
  GUID v7; // xmm0
  GUID v8; // xmm1
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  v3 = a2;
  LOBYTE(a2) = UmpoOnAcPower;
  Uuid = 0;
  result = UmpoGetActualOverlayScheme(&Uuid, a2);
  if ( !(_DWORD)result )
  {
    v7 = GUID_POWER_MODE_NONE;
    if ( v3 )
      v8 = GUID_POWER_MODE_BEST_EFFICIENCY;
    else
      v8 = GUID_POWER_MODE_NONE;
    if ( a1 == 1 )
    {
      *a3 = v8;
    }
    else
    {
      if ( !a1 )
        v7 = Uuid;
      *a3 = v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001337c  mov     [rsp+arg_0], rbx
0x180013381  mov     [rsp+arg_8], rsi
0x180013386  push    rdi
0x180013387  sub     rsp, 40h
0x18001338b  mov     rax, cs:__security_cookie
0x180013392  xor     rax, rsp
0x180013395  mov     [rsp+48h+var_18], rax
0x18001339a  mov     sil, dl
0x18001339d  mov     edi, ecx
0x18001339f  mov     dl, cs:UmpoOnAcPower
0x1800133a5  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800133aa  xorps   xmm0, xmm0
0x1800133ad  mov     rbx, r8
0x1800133b0  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800133b5  call    UmpoGetActualOverlayScheme
0x1800133ba  test    eax, eax
0x1800133bc  jnz     short loc_1800133EE
0x1800133be  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_NONE.Data1
0x1800133c5  test    sil, sil
0x1800133c8  jz      short loc_1800133D3
0x1800133ca  movups  xmm1, xmmword ptr cs:GUID_POWER_MODE_BEST_EFFICIENCY.Data1
0x1800133d1  jmp     short loc_1800133D6
0x1800133d3  movups  xmm1, xmm0
0x1800133d6  cmp     edi, 1
0x1800133d9  jnz     short loc_1800133E1
0x1800133db  movdqu  xmmword ptr [rbx], xmm1
0x1800133df  jmp     short loc_1800133EE
0x1800133e1  test    edi, edi
0x1800133e3  jnz     short loc_1800133EA
0x1800133e5  movups  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800133ea  movdqu  xmmword ptr [rbx], xmm0
0x1800133ee  mov     rcx, [rsp+48h+var_18]
0x1800133f3  xor     rcx, rsp; StackCookie
0x1800133f6  call    __security_check_cookie
0x1800133fb  mov     rbx, [rsp+48h+arg_0]
0x180013400  mov     rsi, [rsp+48h+arg_8]
0x180013405  add     rsp, 40h
0x180013409  pop     rdi
0x18001340a  retn
```
