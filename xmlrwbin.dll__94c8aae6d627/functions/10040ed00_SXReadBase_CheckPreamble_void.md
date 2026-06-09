# SXReadBase::CheckPreamble(void)

- ea: `0x10040ed00`
- end: `0x10040ed9e`
- name: `?CheckPreamble@SXReadBase@@IEAAXXZ`
- size: `158`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10040edb0`

## callees

- `0x100401350`
- `0x10040ed00`
- `0x100411000`
- `0x100414090`
- `0x100416590`

## pseudocode

```c
void __fastcall SXReadBase::CheckPreamble(SXReadBase *this)
{
  __int16 v1; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 v2; // [rsp+42h] [rbp-16h]
  char v3; // [rsp+43h] [rbp-15h]
  char v4; // [rsp+44h] [rbp-14h]

  SXReadBase::GetBytes(this, (unsigned __int8 *)&v1, 5u);
  if ( v1 != 16984 && v1 != -33 || v2 > 1u )
  {
    MXRRaiseException(-2147467259);
    MXRRaiseException(-1072896680);
    __debugbreak();
  }
  if ( v3 != -80 || v4 != 4 )
  {
    MXRRaiseException(-2147024809);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x10040ed00  sub     rsp, 58h
0x10040ed04  mov     rax, cs:__security_cookie
0x10040ed0b  xor     rax, rsp
0x10040ed0e  mov     [rsp+58h+var_10], rax
0x10040ed13  mov     r8d, 5; unsigned int
0x10040ed19  lea     rdx, [rsp+58h+var_18]; unsigned __int8 *
0x10040ed1e  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040ed23  nop
0x10040ed24  movzx   ecx, byte ptr [rsp+58h+var_18]
0x10040ed29  movzx   eax, byte ptr [rsp+58h+var_18+1]
0x10040ed2e  cmp     cl, 58h ; 'X'
0x10040ed31  jnz     short loc_10040ED37
0x10040ed33  cmp     al, 42h ; 'B'
0x10040ed35  jz      short loc_10040ED40
0x10040ed37  cmp     cl, 0DFh
0x10040ed3a  jnz     short loc_10040ED82
0x10040ed3c  cmp     al, 0FFh
0x10040ed3e  jnz     short loc_10040ED82
0x10040ed40  cmp     [rsp+58h+var_16], 1
0x10040ed45  ja      short loc_10040ED82
0x10040ed47  cmp     [rsp+58h+var_15], 0B0h
0x10040ed4c  jnz     short loc_10040ED77
0x10040ed4e  cmp     [rsp+58h+var_14], 4
0x10040ed53  jnz     short loc_10040ED77
0x10040ed55  jmp     short loc_10040ED65
0x10040ed57  mov     ecx, [rsp+58h+var_38]; int
0x10040ed5b  cmp     ecx, 0C00CE559h
0x10040ed61  jnz     short loc_10040ED98
0x10040ed63  jmp     short loc_10040ED8D
0x10040ed65  mov     rcx, [rsp+58h+var_10]
0x10040ed6a  xor     rcx, rsp; StackCookie
0x10040ed6d  call    __security_check_cookie
0x10040ed72  add     rsp, 58h
0x10040ed76  retn
0x10040ed77  mov     ecx, 80070057h; int
0x10040ed7c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ed81  int     3; Trap to Debugger
0x10040ed82  mov     ecx, 80004005h; int
0x10040ed87  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ed8c  nop
0x10040ed8d  mov     ecx, 0C00CE558h; int
0x10040ed92  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ed97  int     3; Trap to Debugger
0x10040ed98  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040ed9d  nop
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
