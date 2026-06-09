# Scanner::ScanComment(void)

- ea: `0x1004104a0`
- end: `0x10041051b`
- name: `?ScanComment@Scanner@@AEAAXXZ`
- size: `123`
- prototype: `void __fastcall(Scanner *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100412dc0`
- `0x1004134e0`
- `0x1004136f0`

## callees

- `0x100401780`
- `0x10040ca10`
- `0x1004104a0`
- `0x100439df0`

## pseudocode

```c
void __fastcall Scanner::ScanComment(Scanner *this)
{
  __int16 v2; // ax
  __int64 v3; // rcx

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  *((_WORD *)this + 92) = v2;
  if ( v2 != 45 )
  {
    MXRRaiseException(-1072894417);
    JUMPOUT(0x10041051ALL);
  }
  *((_DWORD *)this + 18) = 15;
  v3 = *((unsigned int *)this + 26);
  if ( *((_DWORD *)this + 27) == (_DWORD)v3 )
  {
    _stack<void (Scanner::*)(void),8>::grow((__int64)this + 80, 0);
    v3 = *((unsigned int *)this + 26);
  }
  *((_DWORD *)this + 26) = v3 + 1;
  *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v3) = Scanner::ScanCommentData;
  *((_QWORD *)this + 22) = Scanner::ScanCommentData;
}

```

## disassembly

```asm
0x1004104a0  push    rdi
0x1004104a2  sub     rsp, 20h
0x1004104a6  mov     rdi, rcx
0x1004104a9  mov     rcx, [rcx+40h]
0x1004104ad  mov     rax, [rcx]
0x1004104b0  mov     rax, [rax+58h]
0x1004104b4  call    cs:__guard_dispatch_icall_fptr
0x1004104ba  mov     [rdi+0B8h], ax
0x1004104c1  cmp     ax, 2Dh ; '-'
0x1004104c5  jnz     short loc_100410510
0x1004104c7  mov     dword ptr [rdi+48h], 0Fh
0x1004104ce  mov     ecx, [rdi+68h]
0x1004104d1  mov     [rsp+28h+arg_0], rbx
0x1004104d6  cmp     [rdi+6Ch], ecx
0x1004104d9  jnz     short loc_1004104E9
0x1004104db  xor     edx, edx
0x1004104dd  lea     rcx, [rdi+50h]
0x1004104e1  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x1004104e6  mov     ecx, [rdi+68h]
0x1004104e9  mov     rbx, [rsp+28h+arg_0]
0x1004104ee  lea     eax, [rcx+1]
0x1004104f1  mov     [rdi+68h], eax
0x1004104f4  lea     rdx, ?ScanCommentData@Scanner@@AEAAXXZ; Scanner::ScanCommentData(void)
0x1004104fb  mov     rax, [rdi+60h]
0x1004104ff  mov     [rax+rcx*8], rdx
0x100410503  mov     [rdi+0B0h], rdx
0x10041050a  add     rsp, 20h
0x10041050e  pop     rdi
0x10041050f  retn
0x100410510  mov     ecx, 0C00CEE2Fh; int
0x100410515  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
