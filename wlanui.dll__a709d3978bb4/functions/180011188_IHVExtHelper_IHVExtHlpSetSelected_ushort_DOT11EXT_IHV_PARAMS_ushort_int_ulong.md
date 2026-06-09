# IHVExtHelper::IHVExtHlpSetSelected(ushort *,_DOT11EXT_IHV_PARAMS *,ushort * *,int *,ulong)

- ea: `0x180011188`
- end: `0x18001121b`
- name: `?IHVExtHlpSetSelected@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@PEAPEAGPEAHK@Z`
- size: `147`
- prototype: `__int64 __usercall@<rax>(IHVExtHelper *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct _DOT11EXT_IHV_PARAMS *@<r8>, unsigned __int16 **@<r9>, int *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180009380`
- `0x18000a690`
- `0x18000d714`
- `0x18000df1c`

## callees

- `0x180010f64`
- `0x180011188`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall IHVExtHelper::IHVExtHlpSetSelected(
        IHVExtHelper *this,
        unsigned __int16 *a2,
        struct _DOT11EXT_IHV_PARAMS *a3,
        unsigned __int16 **a4,
        int *a5,
        unsigned int a6)
{
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rcx
  int v12; // ebp
  int v13; // r9d

  if ( a6 )
    v9 = a6 - *((_DWORD *)this + 9);
  else
    v9 = 0;
  *((_DWORD *)this + 3) = v9;
  v10 = (_QWORD *)*((_QWORD *)this + 3);
  if ( !v10 || !*v10 )
    return 2147500035LL;
  v11 = *(_QWORD *)(*(_QWORD *)this + 8LL * v9);
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v11 + 48LL))(v11, a2);
  if ( v12 >= 0 )
  {
    if ( *a5 )
    {
      v13 = *((_DWORD *)this + 9);
      *((_DWORD *)this + 8) = 1;
      IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(this, *a4, a3, v13);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180011188  push    rbx
0x18001118a  push    rbp
0x18001118b  push    rsi
0x18001118c  push    rdi
0x18001118d  push    r14
0x18001118f  sub     rsp, 30h
0x180011193  mov     eax, [rsp+58h+arg_28]
0x18001119a  mov     rdi, r9
0x18001119d  mov     rsi, r8
0x1800111a0  mov     rbx, rcx
0x1800111a3  test    eax, eax
0x1800111a5  jz      short loc_1800111AC
0x1800111a7  sub     eax, [rcx+24h]
0x1800111aa  jmp     short loc_1800111AE
0x1800111ac  xor     eax, eax
0x1800111ae  mov     [rcx+0Ch], eax
0x1800111b1  mov     rcx, [rcx+18h]
0x1800111b5  test    rcx, rcx
0x1800111b8  jz      short loc_18001120B
0x1800111ba  cmp     qword ptr [rcx], 0
0x1800111be  jz      short loc_18001120B
0x1800111c0  mov     r14, [rsp+58h+arg_20]
0x1800111c8  mov     ecx, eax
0x1800111ca  mov     rax, [rbx]
0x1800111cd  mov     [rsp+58h+var_38], r14
0x1800111d2  mov     rcx, [rax+rcx*8]
0x1800111d6  mov     rax, [rcx]
0x1800111d9  mov     rax, [rax+30h]
0x1800111dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111e2  mov     ebp, eax
0x1800111e4  test    eax, eax
0x1800111e6  js      short loc_180011207
0x1800111e8  cmp     dword ptr [r14], 0
0x1800111ec  jz      short loc_180011207
0x1800111ee  mov     r9d, [rbx+24h]; unsigned int
0x1800111f2  mov     r8, rsi; struct _DOT11EXT_IHV_PARAMS *
0x1800111f5  mov     dword ptr [rbx+20h], 1
0x1800111fc  mov     rcx, rbx; this
0x1800111ff  mov     rdx, [rdi]; unsigned __int16 *
0x180011202  call    ?IHVExtHlpLoadPropertyDisplayInfo@IHVExtHelper@@QEAAJPEAGPEAU_DOT11EXT_IHV_PARAMS@@K@Z; IHVExtHelper::IHVExtHlpLoadPropertyDisplayInfo(ushort *,_DOT11EXT_IHV_PARAMS *,ulong)
0x180011207  mov     eax, ebp
0x180011209  jmp     short loc_180011210
0x18001120b  mov     eax, 80004003h
0x180011210  add     rsp, 30h
0x180011214  pop     r14
0x180011216  pop     rdi
0x180011217  pop     rsi
0x180011218  pop     rbp
0x180011219  pop     rbx
0x18001121a  retn
```
