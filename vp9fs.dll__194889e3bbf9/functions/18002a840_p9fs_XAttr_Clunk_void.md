# p9fs::XAttr::Clunk(void)

- ea: `0x18002a840`
- end: `0x18002a918`
- name: `?Clunk@XAttr@p9fs@@UEAAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(p9fs::XAttr *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004120`
- `0x18002a840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a870`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a8f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a8f8`
- `lxutil!LxUtilXattrRemove` at `0x18002a8bb`
- `lxutil!LxUtilXattrRemove` at `0x18002a8bb`
- `lxutil!LxUtilXattrSet` at `0x18002a8e8`
- `lxutil!LxUtilXattrSet` at `0x18002a8e8`

## pseudocode

```c
__int64 __fastcall p9fs::XAttr::Clunk(p9fs::XAttr *this)
{
  RTL_SRWLOCK *v3; // rdi
  _QWORD *v4; // rax
  bool v5; // cc
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int128 v12; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v13[3]; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 20) != 1 )
    return 0;
  v3 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockShared((PSRWLOCK)this + 1);
  v4 = (_QWORD *)((char *)this + 24);
  v5 = *((_QWORD *)this + 6) <= 0xFu;
  v12 = 0;
  if ( !v5 )
    v4 = (_QWORD *)*v4;
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)&v12 + 1) = v4;
  LOWORD(v12) = *((_WORD *)this + 20);
  WORD1(v12) = v12;
  v7 = *((_QWORD *)this + 8) - v6;
  if ( v7 || *((_DWORD *)this + 21) != 2 )
  {
    v9 = *((unsigned int *)this + 21);
    v13[0] = v6;
    v10 = *((_QWORD *)this + 2);
    v13[2] = 0;
    v13[1] = v7;
    v8 = ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD *, __int64))LxUtilXattrSet)(v10, &v12, v13, v9);
  }
  else
  {
    v8 = LxUtilXattrRemove(*((_QWORD *)this + 2), &v12);
  }
  v11 = v8;
  if ( v3 )
    ReleaseSRWLockShared(v3);
  return v11;
}

```

## disassembly

```asm
0x18002a840  mov     [rsp+arg_8], rbx
0x18002a845  push    rdi
0x18002a846  sub     rsp, 50h
0x18002a84a  mov     rax, cs:__security_cookie
0x18002a851  xor     rax, rsp
0x18002a854  mov     [rsp+58h+var_10], rax
0x18002a859  cmp     dword ptr [rcx+50h], 1
0x18002a85d  mov     rbx, rcx
0x18002a860  jz      short loc_18002A869
0x18002a862  xor     eax, eax
0x18002a864  jmp     loc_18002A900
0x18002a869  lea     rdi, [rcx+8]
0x18002a86d  mov     rcx, rdi; SRWLock
0x18002a870  call    cs:__imp_AcquireSRWLockShared
0x18002a876  lea     rax, [rbx+18h]
0x18002a87a  xorps   xmm0, xmm0
0x18002a87d  cmp     qword ptr [rax+18h], 0Fh
0x18002a882  movups  [rsp+58h+var_38], xmm0
0x18002a887  jbe     short loc_18002A88C
0x18002a889  mov     rax, [rax]
0x18002a88c  mov     rcx, [rbx+38h]
0x18002a890  mov     qword ptr [rsp+58h+var_38+8], rax
0x18002a895  movzx   eax, word ptr [rbx+28h]
0x18002a899  mov     word ptr [rsp+58h+var_38], ax
0x18002a89e  mov     word ptr [rsp+58h+var_38+2], ax
0x18002a8a3  mov     rax, [rbx+40h]
0x18002a8a7  sub     rax, rcx
0x18002a8aa  jnz     short loc_18002A8C3
0x18002a8ac  cmp     dword ptr [rbx+54h], 2
0x18002a8b0  jnz     short loc_18002A8C3
0x18002a8b2  mov     rcx, [rbx+10h]
0x18002a8b6  lea     rdx, [rsp+58h+var_38]
0x18002a8bb  call    cs:__imp_LxUtilXattrRemove
0x18002a8c1  jmp     short loc_18002A8EE
0x18002a8c3  mov     r9d, [rbx+54h]
0x18002a8c7  lea     r8, [rsp+58h+var_28]
0x18002a8cc  mov     [rsp+58h+var_28], rcx
0x18002a8d1  lea     rdx, [rsp+58h+var_38]
0x18002a8d6  mov     rcx, [rbx+10h]
0x18002a8da  mov     [rsp+58h+var_18], 0
0x18002a8e3  mov     [rsp+58h+var_20], rax
0x18002a8e8  call    cs:__imp_LxUtilXattrSet
0x18002a8ee  mov     ebx, eax
0x18002a8f0  test    rdi, rdi
0x18002a8f3  jz      short loc_18002A8FE
0x18002a8f5  mov     rcx, rdi; SRWLock
0x18002a8f8  call    cs:__imp_ReleaseSRWLockShared
0x18002a8fe  mov     eax, ebx
0x18002a900  mov     rcx, [rsp+58h+var_10]
0x18002a905  xor     rcx, rsp; StackCookie
0x18002a908  call    __security_check_cookie
0x18002a90d  mov     rbx, [rsp+58h+arg_8]
0x18002a912  add     rsp, 50h
0x18002a916  pop     rdi
0x18002a917  retn
```
