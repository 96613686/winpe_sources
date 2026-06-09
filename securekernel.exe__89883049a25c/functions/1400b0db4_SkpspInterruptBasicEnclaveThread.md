# SkpspInterruptBasicEnclaveThread

- ea: `0x1400b0db4`
- end: `0x1400b0ee0`
- name: `SkpspInterruptBasicEnclaveThread`
- size: `300`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140021428`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140002ef0`
- `0x140036534`
- `0x14009b778`
- `0x1400b0db4`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpspInterruptBasicEnclaveThread(__int64 a1)
{
  _QWORD *StackBase; // rdi
  __int64 v3; // rbx
  char *v5; // rsi
  char v6; // al
  __int64 v7; // rdx
  signed int v8; // edi
  __int64 v9; // rax
  signed __int32 v10[64]; // [rsp+20h] [rbp-118h] BYREF

  memset_0(v10, 0, sizeof(v10));
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    StackBase = (_QWORD *)StackBase[10];
  v3 = SkpspReferenceBasicEnclaveThread(StackBase, a1, 0);
  if ( !v3 )
    return 3221225485LL;
  v5 = (char *)(StackBase + 27);
  v6 = SkAcquireSpinLockExclusive(StackBase + 27);
  if ( (*(_DWORD *)(v3 + 172) & 0x2400) != 0 )
    v8 = -1073740522;
  else
    v8 = _interlockedbittestandset((volatile signed __int32 *)(v3 + 172), 0xCu) != 0 ? 0xC0000718 : 0;
  LOBYTE(v7) = v6;
  SkReleaseSpinLockExclusive(v5, v7);
  if ( v8 >= 0 )
  {
    memset_0(v10, 0, sizeof(v10));
    v9 = *(_QWORD *)(v3 + 64);
    if ( v9 )
    {
      _interlockedbittestandset(
        &v10[(unsigned __int64)*(unsigned __int16 *)(v9 + 180) >> 5],
        *(_WORD *)(v9 + 180) & 0x1F);
      SkeGenericIpiCall(v10, 0, 0, 0);
    }
  }
  SkobDereferenceObject(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400b0db4  mov     [rsp+arg_8], rbx
0x1400b0db9  mov     [rsp+arg_10], rsi
0x1400b0dbe  push    rdi
0x1400b0dbf  sub     rsp, 130h
0x1400b0dc6  mov     rax, cs:__security_cookie
0x1400b0dcd  xor     rax, rsp
0x1400b0dd0  mov     [rsp+138h+var_18], rax
0x1400b0dd8  mov     rbx, rcx
0x1400b0ddb  xor     edx, edx; Val
0x1400b0ddd  lea     rcx, [rsp+138h+var_118]; void *
0x1400b0de2  mov     r8d, 100h; Size
0x1400b0de8  call    memset_0
0x1400b0ded  mov     rdi, gs:8
0x1400b0df6  test    rdi, rdi
0x1400b0df9  jz      short loc_1400B0DFF
0x1400b0dfb  mov     rdi, [rdi+50h]
0x1400b0dff  xor     r8d, r8d
0x1400b0e02  mov     rdx, rbx
0x1400b0e05  mov     rcx, rdi
0x1400b0e08  call    SkpspReferenceBasicEnclaveThread
0x1400b0e0d  mov     rbx, rax
0x1400b0e10  test    rax, rax
0x1400b0e13  jnz     short loc_1400B0E1F
0x1400b0e15  mov     eax, 0C000000Dh
0x1400b0e1a  jmp     loc_1400B0EBA
0x1400b0e1f  lea     rsi, [rdi+0D8h]
0x1400b0e26  mov     rcx, rsi
0x1400b0e29  call    SkAcquireSpinLockExclusive
0x1400b0e2e  test    dword ptr [rbx+0ACh], 2400h
0x1400b0e38  jnz     short loc_1400B0E5A
0x1400b0e3a  lock bts dword ptr [rbx+0ACh], 0Ch
0x1400b0e43  setb    dl
0x1400b0e46  xor     ecx, ecx
0x1400b0e48  sub     cl, dl
0x1400b0e4a  mov     r8b, cl
0x1400b0e4d  neg     r8b
0x1400b0e50  sbb     edi, edi
0x1400b0e52  and     edi, 0C0000718h
0x1400b0e58  jmp     short loc_1400B0E5F
0x1400b0e5a  mov     edi, 0C0000516h
0x1400b0e5f  mov     dl, al
0x1400b0e61  mov     rcx, rsi
0x1400b0e64  call    SkReleaseSpinLockExclusive
0x1400b0e69  test    edi, edi
0x1400b0e6b  js      short loc_1400B0EB0
0x1400b0e6d  xor     edx, edx; Val
0x1400b0e6f  lea     rcx, [rsp+138h+var_118]; void *
0x1400b0e74  mov     r8d, 100h; Size
0x1400b0e7a  call    memset_0
0x1400b0e7f  mov     rax, [rbx+40h]
0x1400b0e83  test    rax, rax
0x1400b0e86  jz      short loc_1400B0EB0
0x1400b0e88  movzx   edx, word ptr [rax+0B4h]
0x1400b0e8f  xor     r9d, r9d
0x1400b0e92  mov     ecx, edx
0x1400b0e94  xor     r8d, r8d
0x1400b0e97  shr     rdx, 5
0x1400b0e9b  and     ecx, 1Fh
0x1400b0e9e  lock bts [rsp+rdx*4+138h+var_118], ecx
0x1400b0ea4  xor     edx, edx
0x1400b0ea6  lea     rcx, [rsp+138h+var_118]
0x1400b0eab  call    SkeGenericIpiCall
0x1400b0eb0  mov     rcx, rbx
0x1400b0eb3  call    SkobDereferenceObject
0x1400b0eb8  mov     eax, edi
0x1400b0eba  mov     rcx, [rsp+138h+var_18]
0x1400b0ec2  xor     rcx, rsp; StackCookie
0x1400b0ec5  call    __security_check_cookie
0x1400b0eca  lea     r11, [rsp+138h+var_8]
0x1400b0ed2  mov     rbx, [r11+18h]
0x1400b0ed6  mov     rsi, [r11+20h]
0x1400b0eda  mov     rsp, r11
0x1400b0edd  pop     rdi
0x1400b0ede  retn
```
