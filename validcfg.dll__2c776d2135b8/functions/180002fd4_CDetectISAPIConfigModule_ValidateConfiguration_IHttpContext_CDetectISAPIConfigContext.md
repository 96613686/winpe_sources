# CDetectISAPIConfigModule::ValidateConfiguration(IHttpContext *,CDetectISAPIConfigContext *)

- ea: `0x180002fd4`
- end: `0x180003092`
- name: `?ValidateConfiguration@CDetectISAPIConfigModule@@AEAAJPEAVIHttpContext@@PEAVCDetectISAPIConfigContext@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(CDetectISAPIConfigModule *__hidden this, struct IHttpContext *, struct CDetectISAPIConfigContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001510`

## callees

- `0x180002fd4`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CDetectISAPIConfigModule::ValidateConfiguration(
        CDetectISAPIConfigModule *this,
        struct IHttpContext *a2,
        struct CDetectISAPIConfigContext *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  __int64 result; // rax

  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( *((_DWORD *)a3 + 3) )
  {
    v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    v4 = 22;
  }
  else if ( *((_DWORD *)a3 + 4) )
  {
    v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    v4 = 23;
  }
  else
  {
    if ( !*((_DWORD *)a3 + 5) )
      return 0;
    v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    v4 = 24;
  }
  result = (*(__int64 (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v3 + 24LL))(
             v3,
             500,
             "Internal Server Error",
             v4,
             -2147024846,
             0,
             0);
  if ( (int)result >= 0 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180002fd4  sub     rsp, 48h
0x180002fd8  test    rdx, rdx
0x180002fdb  jz      loc_180003088
0x180002fe1  test    r8, r8
0x180002fe4  jz      loc_180003088
0x180002fea  cmp     dword ptr [r8+0Ch], 0
0x180002fef  jz      short loc_180003008
0x180002ff1  mov     rax, [rdx]
0x180002ff4  mov     rcx, rdx
0x180002ff7  mov     rax, [rax+20h]
0x180002ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003000  mov     r9d, 16h
0x180003006  jmp     short loc_180003042
0x180003008  cmp     dword ptr [r8+10h], 0
0x18000300d  jz      short loc_180003026
0x18000300f  mov     rax, [rdx]
0x180003012  mov     rcx, rdx
0x180003015  mov     rax, [rax+20h]
0x180003019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301e  mov     r9d, 17h
0x180003024  jmp     short loc_180003042
0x180003026  cmp     dword ptr [r8+14h], 0
0x18000302b  jz      short loc_180003084
0x18000302d  mov     rax, [rdx]
0x180003030  mov     rcx, rdx
0x180003033  mov     rax, [rax+20h]
0x180003037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303c  mov     r9d, 18h
0x180003042  mov     rcx, [rax]
0x180003045  lea     r8, aInternalServer; "Internal Server Error"
0x18000304c  mov     r10, rax
0x18000304f  mov     [rsp+48h+var_18], 0
0x180003057  mov     [rsp+48h+var_20], 0
0x180003060  mov     edx, 1F4h
0x180003065  mov     [rsp+48h+var_28], 80070032h
0x18000306d  mov     rax, [rcx+18h]
0x180003071  mov     rcx, r10
0x180003074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003079  test    eax, eax
0x18000307b  js      short loc_18000308D
0x18000307d  mov     eax, 1
0x180003082  jmp     short loc_18000308D
0x180003084  xor     eax, eax
0x180003086  jmp     short loc_18000308D
0x180003088  mov     eax, 80070057h
0x18000308d  add     rsp, 48h
0x180003091  retn
```
