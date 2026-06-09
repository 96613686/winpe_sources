# CWdsSimpleDeviceQueryResult::MoveToIndex(ulong)

- ea: `0x1800075e0`
- end: `0x18000764e`
- name: `?MoveToIndex@CWdsSimpleDeviceQueryResult@@UEAAJK@Z`
- size: `110`
- prototype: `__int64 __fastcall(CWdsSimpleDeviceQueryResult *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005508`
- `0x1800075e0`
- `0x180007808`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800075ff`
- `KERNEL32!EnterCriticalSection` at `0x1800075ff`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceQueryResult::MoveToIndex(CWdsSimpleDeviceQueryResult *this, unsigned int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  char *v8; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+28h] [rbp-10h]

  v4 = 0;
  v8 = (char *)this + 104;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v9 = 1;
  if ( a2 < *((_DWORD *)this + 19) || (v4 = -2147024809, (int)ElValidateHr_0(2147942487LL, v5, v6, 384) >= 0) )
    *((_DWORD *)this + 24) = a2;
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v8);
  return v4;
}

```

## disassembly

```asm
0x1800075e0  mov     [rsp+arg_0], rbx
0x1800075e5  mov     [rsp+arg_8], rsi
0x1800075ea  push    rdi
0x1800075eb  sub     rsp, 30h
0x1800075ef  mov     rbx, rcx
0x1800075f2  mov     esi, edx
0x1800075f4  add     rcx, 68h ; 'h'; lpCriticalSection
0x1800075f8  xor     edi, edi
0x1800075fa  mov     [rsp+38h+var_18], rcx
0x1800075ff  call    cs:__imp_EnterCriticalSection
0x180007606  nop     dword ptr [rax+rax+00h]
0x18000760b  mov     [rsp+38h+var_10], 1
0x180007613  cmp     esi, [rbx+4Ch]
0x180007616  jb      short loc_18000762E
0x180007618  mov     edi, 80070057h
0x18000761d  mov     r9d, 180h
0x180007623  mov     ecx, edi
0x180007625  call    ElValidateHr_0
0x18000762a  test    eax, eax
0x18000762c  js      short loc_180007631
0x18000762e  mov     [rbx+60h], esi
0x180007631  lea     rcx, [rsp+38h+var_18]
0x180007636  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000763b  mov     rbx, [rsp+38h+arg_0]
0x180007640  mov     eax, edi
0x180007642  mov     rsi, [rsp+38h+arg_8]
0x180007647  add     rsp, 30h
0x18000764b  pop     rdi
0x18000764c  retn
```
