# SIPolicyCommitState

- ea: `0x18001c2b8`
- end: `0x18001c37a`
- name: `SIPolicyCommitState`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019cd0`
- `0x18001c6d4`
- `0x1800492f8`

## callees

- `0x18001c2b8`
- `0x18002019c`

## import_xrefs

- `securekernel!SkReleasePushLockExclusive` at `0x18001c35d`
- `securekernel!SkReleasePushLockExclusive` at `0x18001c35d`
- `securekernel!SkAcquirePushLockExclusive` at `0x18001c322`
- `securekernel!SkAcquirePushLockExclusive` at `0x18001c322`

## pseudocode

```c
__int64 __fastcall SIPolicyCommitState(_QWORD **a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx

  v2 = (_QWORD *)(**a1 + 32LL);
  v3 = (_QWORD *)*v2;
  if ( (_QWORD *)*v2 != v2 )
  {
    v4 = (_QWORD *)*v3;
    v5 = (_QWORD *)*v3;
    while ( 1 )
    {
      if ( (_QWORD *)v5[1] != v3 || (v6 = (_QWORD *)v3[1], (_QWORD *)*v6 != v3) )
        __fastfail(3u);
      *v6 = v5;
      v5[1] = v6;
      SIPolicyUninitialize(v3 - 104);
      if ( v4 == v2 )
        break;
      v5 = (_QWORD *)*v4;
      v3 = v4;
      v4 = (_QWORD *)*v4;
    }
  }
  SkAcquirePushLockExclusive(&qword_18003F580);
  v7 = *a1;
  *a1 = (_QWORD *)qword_18003F598;
  qword_18003F598 = (__int64)v7;
  g_SiPolicyHandles = v7[5];
  g_NumberOfSiPolicies = *((_DWORD *)v7 + 9);
  return SkReleasePushLockExclusive(&qword_18003F580);
}

```

## disassembly

```asm
0x18001c2b8  mov     [rsp+arg_0], rbx
0x18001c2bd  mov     [rsp+arg_8], rsi
0x18001c2c2  push    rdi
0x18001c2c3  sub     rsp, 20h
0x18001c2c7  mov     rax, [rcx]
0x18001c2ca  mov     rsi, rcx
0x18001c2cd  mov     rdi, [rax]
0x18001c2d0  add     rdi, 20h ; ' '
0x18001c2d4  mov     rcx, [rdi]
0x18001c2d7  cmp     rcx, rdi
0x18001c2da  jz      short loc_18001C31B
0x18001c2dc  mov     rbx, [rcx]
0x18001c2df  mov     rax, rbx
0x18001c2e2  cmp     [rax+8], rcx
0x18001c2e6  jnz     short loc_18001C314
0x18001c2e8  mov     rdx, [rcx+8]
0x18001c2ec  cmp     [rdx], rcx
0x18001c2ef  jnz     short loc_18001C314
0x18001c2f1  mov     [rdx], rax
0x18001c2f4  add     rcx, 0FFFFFFFFFFFFFCC0h
0x18001c2fb  mov     [rax+8], rdx
0x18001c2ff  call    SIPolicyUninitialize
0x18001c304  cmp     rbx, rdi
0x18001c307  jz      short loc_18001C31B
0x18001c309  mov     rax, [rbx]
0x18001c30c  mov     rcx, rbx
0x18001c30f  mov     rbx, rax
0x18001c312  jmp     short loc_18001C2E2
0x18001c314  mov     ecx, 3
0x18001c319  int     29h; Win8: RtlFailFast(ecx)
0x18001c31b  lea     rcx, qword_18003F580
0x18001c322  call    cs:__imp_SkAcquirePushLockExclusive
0x18001c329  nop     dword ptr [rax+rax+00h]
0x18001c32e  mov     rdx, [rsi]
0x18001c331  lea     rcx, qword_18003F580
0x18001c338  mov     rax, cs:qword_18003F598
0x18001c33f  mov     [rsi], rax
0x18001c342  mov     cs:qword_18003F598, rdx
0x18001c349  mov     rax, [rdx+28h]
0x18001c34d  mov     cs:g_SiPolicyHandles, rax
0x18001c354  mov     eax, [rdx+24h]
0x18001c357  mov     cs:g_NumberOfSiPolicies, eax
0x18001c35d  call    cs:__imp_SkReleasePushLockExclusive
0x18001c364  nop     dword ptr [rax+rax+00h]
0x18001c369  mov     rbx, [rsp+28h+arg_0]
0x18001c36e  mov     rsi, [rsp+28h+arg_8]
0x18001c373  add     rsp, 20h
0x18001c377  pop     rdi
0x18001c378  retn
```
