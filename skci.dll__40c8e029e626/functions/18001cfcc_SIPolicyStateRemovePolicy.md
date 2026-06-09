# SIPolicyStateRemovePolicy

- ea: `0x18001cfcc`
- end: `0x18001d05c`
- name: `SIPolicyStateRemovePolicy`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800492f8`

## callees

- `0x18001ccc4`
- `0x18001cfcc`

## import_xrefs

- `securekernel!SkReleasePushLockExclusive` at `0x18001d03d`
- `securekernel!SkReleasePushLockExclusive` at `0x18001d03d`
- `securekernel!SkAcquirePushLockExclusive` at `0x18001cfdc`
- `securekernel!SkAcquirePushLockExclusive` at `0x18001cfdc`

## pseudocode

```c
__int64 __fastcall SIPolicyStateRemovePolicy(__int64 a1, __int64 a2)
{
  __int64 Policy; // rax
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // r8

  SkAcquirePushLockExclusive(a1);
  Policy = SIPolicyStateFindPolicy(a1, a2);
  if ( Policy )
  {
    v5 = (_QWORD *)(Policy + 832);
    v6 = *(_QWORD *)(Policy + 832);
    if ( *(_QWORD *)(v6 + 8) != Policy + 832
      || (v7 = *(_QWORD **)(Policy + 840), (_QWORD *)*v7 != v5)
      || (*v7 = v6,
          *(_QWORD *)(v6 + 8) = v7,
          v8 = (_QWORD *)(a1 + 32),
          v9 = *(_QWORD *)(a1 + 32),
          *(_QWORD *)(v9 + 8) != a1 + 32) )
    {
      __fastfail(3u);
    }
    *v5 = v9;
    *(_QWORD *)(Policy + 840) = v8;
    *(_QWORD *)(v9 + 8) = v5;
    *v8 = v5;
    *(_DWORD *)(Policy + 672) |= 0x10u;
  }
  return SkReleasePushLockExclusive(a1);
}

```

## disassembly

```asm
0x18001cfcc  mov     [rsp+arg_0], rbx
0x18001cfd1  push    rdi
0x18001cfd2  sub     rsp, 20h
0x18001cfd6  mov     rbx, rdx
0x18001cfd9  mov     rdi, rcx
0x18001cfdc  call    cs:__imp_SkAcquirePushLockExclusive
0x18001cfe3  nop     dword ptr [rax+rax+00h]
0x18001cfe8  mov     rdx, rbx
0x18001cfeb  mov     rcx, rdi
0x18001cfee  call    SIPolicyStateFindPolicy
0x18001cff3  test    rax, rax
0x18001cff6  jz      short loc_18001D03A
0x18001cff8  lea     rdx, [rax+340h]
0x18001cfff  mov     rcx, [rdx]
0x18001d002  cmp     [rcx+8], rdx
0x18001d006  jnz     short loc_18001D055
0x18001d008  mov     r8, [rdx+8]
0x18001d00c  cmp     [r8], rdx
0x18001d00f  jnz     short loc_18001D055
0x18001d011  mov     [r8], rcx
0x18001d014  mov     [rcx+8], r8
0x18001d018  lea     rcx, [rdi+20h]
0x18001d01c  mov     r8, [rcx]
0x18001d01f  cmp     [r8+8], rcx
0x18001d023  jnz     short loc_18001D055
0x18001d025  mov     [rdx], r8
0x18001d028  mov     [rdx+8], rcx
0x18001d02c  mov     [r8+8], rdx
0x18001d030  mov     [rcx], rdx
0x18001d033  or      dword ptr [rax+2A0h], 10h
0x18001d03a  mov     rcx, rdi
0x18001d03d  call    cs:__imp_SkReleasePushLockExclusive
0x18001d044  nop     dword ptr [rax+rax+00h]
0x18001d049  mov     rbx, [rsp+28h+arg_0]
0x18001d04e  add     rsp, 20h
0x18001d052  pop     rdi
0x18001d053  retn
0x18001d055  mov     ecx, 3
0x18001d05a  int     29h; Win8: RtlFailFast(ecx)
```
