# VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)

- ea: `0x18001f414`
- end: `0x18001f4cd`
- name: `?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001f1ec`
- `0x18001f2f4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001ef88`
- `0x18001f414`

## string_xrefs

- `0x18001f42b`: `VerifyTokenMembership`

## pseudocode

```c
__int64 __fastcall VerifyTokenMembership(HANDLE TokenHandle, WELL_KNOWN_SID_TYPE WellKnownSidType)
{
  __int16 v4; // ax
  int v5; // ebx
  int v7; // [rsp+20h] [rbp-40h] BYREF
  __int16 v8; // [rsp+24h] [rbp-3Ch]
  __int16 v9; // [rsp+26h] [rbp-3Ah]
  int v10; // [rsp+70h] [rbp+10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "VerifyTokenMembership", 262, 1);
  v10 = 0;
  v4 = 265;
  if ( TokenHandle )
  {
    v7 = 0;
    v8 = 265;
    v5 = IsTokenMember(TokenHandle, WellKnownSidType, &v10);
    v7 = v5;
    v4 = 267;
    if ( v5 < 0 )
      goto LABEL_4;
    v8 = 267;
    v4 = 268;
    if ( v10 )
    {
      v7 = 0;
      v5 = 0;
      v8 = 268;
      goto LABEL_9;
    }
    v5 = -2147024891;
  }
  else
  {
    v5 = -2147024809;
  }
  v7 = v5;
LABEL_4:
  v9 = v4;
LABEL_9:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f414  mov     [rsp-8+arg_8], rbx
0x18001f419  mov     [rsp-8+arg_10], rdi
0x18001f41e  push    rbp
0x18001f41f  mov     rbp, rsp
0x18001f422  sub     rsp, 60h
0x18001f426  mov     edi, edx
0x18001f428  mov     rbx, rcx
0x18001f42b  lea     rdx, aVerifytokenmem; "VerifyTokenMembership"
0x18001f432  mov     r9d, 1; unsigned __int16
0x18001f438  lea     rcx, [rbp+var_40]; this
0x18001f43c  mov     r8d, 106h; unsigned __int16
0x18001f442  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f447  mov     [rbp+arg_0], 0
0x18001f44e  mov     eax, 109h
0x18001f453  test    rbx, rbx
0x18001f456  jnz     short loc_18001F466
0x18001f458  mov     ebx, 80070057h
0x18001f45d  mov     [rbp+var_40], ebx
0x18001f460  mov     [rbp+var_3A], ax
0x18001f464  jmp     short loc_18001F4B0
0x18001f466  lea     r8, [rbp+arg_0]; int *
0x18001f46a  mov     [rbp+var_40], 0
0x18001f471  mov     edx, edi; WellKnownSidType
0x18001f473  mov     [rbp+var_3C], ax
0x18001f477  mov     rcx, rbx; TokenHandle
0x18001f47a  call    ?IsTokenMember@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z; IsTokenMember(void *,WELL_KNOWN_SID_TYPE,int *)
0x18001f47f  mov     ebx, eax
0x18001f481  mov     [rbp+var_40], eax
0x18001f484  test    eax, eax
0x18001f486  mov     eax, 10Bh
0x18001f48b  js      short loc_18001F460
0x18001f48d  cmp     [rbp+arg_0], 0
0x18001f491  mov     [rbp+var_3C], ax
0x18001f495  mov     eax, 10Ch
0x18001f49a  jnz     short loc_18001F4A3
0x18001f49c  mov     ebx, 80070005h
0x18001f4a1  jmp     short loc_18001F45D
0x18001f4a3  mov     [rbp+var_40], 0
0x18001f4aa  xor     ebx, ebx
0x18001f4ac  mov     [rbp+var_3C], ax
0x18001f4b0  lea     rcx, [rbp+var_40]; this
0x18001f4b4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f4b9  lea     r11, [rsp+60h+var_s0]
0x18001f4be  mov     eax, ebx
0x18001f4c0  mov     rbx, [r11+18h]
0x18001f4c4  mov     rdi, [r11+20h]
0x18001f4c8  mov     rsp, r11
0x18001f4cb  pop     rbp
0x18001f4cc  retn
```
