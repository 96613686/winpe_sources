# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800012ac`
- end: `0x180001411`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U1@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@433AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapSz@D@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c30`

## callees

- `0x1800012ac`
- `0x1800016a0`
- `0x1800131e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        _QWORD *a13)
{
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax

  v13 = -1;
  if ( *a13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(*a13 + v14) );
  }
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(*a7 + 2 * v15) );
  }
  if ( *a6 )
  {
    do
      ++v13;
    while ( *(_WORD *)(*a6 + 2 * v13) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001F018, a2, 0);
}

```

## disassembly

```asm
0x1800012ac  push    rbp
0x1800012ae  lea     rbp, [rsp-0Fh]
0x1800012b3  sub     rsp, 0F0h
0x1800012ba  mov     rax, cs:__security_cookie
0x1800012c1  xor     rax, rsp
0x1800012c4  mov     [rbp+0Fh+var_10], rax
0x1800012c8  mov     rax, [rbp+0Fh+arg_60]
0x1800012cc  mov     r10, rdx
0x1800012cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800012d3  xor     r9d, r9d
0x1800012d6  mov     rdx, [rax]
0x1800012d9  test    rdx, rdx
0x1800012dc  jz      short loc_1800012EE
0x1800012de  mov     rax, rcx
0x1800012e1  inc     rax
0x1800012e4  cmp     [rdx+rax], r9b
0x1800012e8  jnz     short loc_1800012E1
0x1800012ea  inc     eax
0x1800012ec  jmp     short loc_1800012FA
0x1800012ee  lea     rdx, dword_1800191A4
0x1800012f5  mov     eax, 1
0x1800012fa  mov     [rbp+0Fh+var_18], eax
0x1800012fd  mov     r8d, 2
0x180001303  mov     rax, [rbp+0Fh+arg_58]
0x180001307  mov     [rbp+0Fh+var_30], rax
0x18000130b  mov     rax, [rbp+0Fh+arg_50]
0x18000130f  mov     [rbp+0Fh+var_40], rax
0x180001313  mov     rax, [rbp+0Fh+arg_48]
0x180001317  mov     [rbp+0Fh+var_50], rax
0x18000131b  mov     rax, [rbp+0Fh+arg_40]
0x18000131f  mov     [rbp+0Fh+var_60], rax
0x180001323  mov     rax, [rbp+0Fh+arg_38]
0x180001327  mov     [rbp+0Fh+var_70], rax
0x18000132b  mov     rax, [rbp+0Fh+arg_30]
0x18000132f  mov     [rbp+0Fh+var_20], rdx
0x180001333  mov     [rbp+0Fh+var_14], r9d
0x180001337  mov     [rbp+0Fh+var_28], 4
0x18000133f  mov     rdx, [rax]
0x180001342  mov     [rbp+0Fh+var_38], 4
0x18000134a  mov     [rbp+0Fh+var_48], 4
0x180001352  mov     [rbp+0Fh+var_58], 8
0x18000135a  mov     [rbp+0Fh+var_68], 8
0x180001362  test    rdx, rdx
0x180001365  jz      short loc_18000137D
0x180001367  mov     rax, rcx
0x18000136a  inc     rax
0x18000136d  cmp     [rdx+rax*2], r9w
0x180001372  jnz     short loc_18000136A
0x180001374  lea     eax, ds:2[rax*2]
0x18000137b  jmp     short loc_180001387
0x18000137d  lea     rdx, dword_180017A6C
0x180001384  mov     eax, r8d
0x180001387  mov     [rbp+0Fh+var_78], eax
0x18000138a  mov     rax, [rbp+0Fh+arg_28]
0x18000138e  mov     [rbp+0Fh+var_80], rdx
0x180001392  mov     [rbp+0Fh+var_74], r9d
0x180001396  mov     rdx, [rax]
0x180001399  test    rdx, rdx
0x18000139c  jz      short loc_1800013B2
0x18000139e  inc     rcx
0x1800013a1  cmp     [rdx+rcx*2], r9w
0x1800013a6  jnz     short loc_18000139E
0x1800013a8  lea     r8d, ds:2[rcx*2]
0x1800013b0  jmp     short loc_1800013B9
0x1800013b2  lea     rdx, dword_180017A6C
0x1800013b9  mov     rax, [rbp+0Fh+arg_20]
0x1800013bd  lea     rcx, dword_18001F018
0x1800013c4  mov     [rsp+0F0h+var_A0], rax
0x1800013c9  lea     rax, [rsp+0F0h+var_C0]
0x1800013ce  mov     [rsp+0F0h+var_90], rdx
0x1800013d3  mov     rdx, r10
0x1800013d6  mov     [rbp+0Fh+var_88], r8d
0x1800013da  xor     r8d, r8d
0x1800013dd  mov     [rsp+0F0h+var_C8], rax
0x1800013e2  mov     [rsp+0F0h+var_D0], 0Bh
0x1800013ea  mov     [rbp+0Fh+var_84], r9d
0x1800013ee  mov     [rsp+0F0h+var_98], 8
0x1800013f7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013fc  mov     rcx, [rbp+0Fh+var_10]
0x180001400  xor     rcx, rsp; StackCookie
0x180001403  call    __security_check_cookie
0x180001408  add     rsp, 0F0h
0x18000140f  pop     rbp
0x180001410  retn
```
