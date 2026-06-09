# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000181c`
- end: `0x180001911`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperArray@$00@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperArray@$00@@5AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012d68`

## callees

- `0x180001260`
- `0x18000181c`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const LPARAM **a6,
        __int64 *a7,
        __int64 *a8,
        __int64 a9)
{
  int v10; // edx
  const LPARAM *v11; // rcx
  __int64 v12; // rax
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-71h] BYREF
  __int64 v15; // [rsp+50h] [rbp-51h]
  __int64 v16; // [rsp+58h] [rbp-49h]
  const LPARAM *v17; // [rsp+60h] [rbp-41h]
  int v18; // [rsp+68h] [rbp-39h]
  int v19; // [rsp+6Ch] [rbp-35h]
  __int64 *v20; // [rsp+70h] [rbp-31h]
  __int64 v21; // [rsp+78h] [rbp-29h]
  __int64 v22; // [rsp+80h] [rbp-21h]
  int v23; // [rsp+88h] [rbp-19h]
  int v24; // [rsp+8Ch] [rbp-15h]
  __int64 *v25; // [rsp+90h] [rbp-11h]
  __int64 v26; // [rsp+98h] [rbp-9h]
  __int64 v27; // [rsp+A0h] [rbp-1h]
  int v28; // [rsp+A8h] [rbp+7h]
  int v29; // [rsp+ACh] [rbp+Bh]
  __int64 v30; // [rsp+B0h] [rbp+Fh]
  __int64 v31; // [rsp+B8h] [rbp+17h]

  v30 = a9;
  v31 = 4;
  v10 = 2;
  v29 = 0;
  v26 = 2;
  v21 = 2;
  v27 = *a8;
  v28 = *((unsigned __int16 *)a8 + 4);
  v25 = a8 + 1;
  v24 = 0;
  v22 = *a7;
  v23 = *((unsigned __int16 *)a7 + 4);
  v20 = a7 + 1;
  v11 = *a6;
  if ( *a6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v10 = 2 * v12 + 2;
  }
  else
  {
    v11 = &lParam;
  }
  v15 = a5;
  v17 = v11;
  v18 = v10;
  v19 = 0;
  v16 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 9u, &v14);
}

```

## disassembly

```asm
0x18000181c  push    rbp
0x18000181e  lea     rbp, [rsp-2Fh]
0x180001823  sub     rsp, 0D0h
0x18000182a  mov     rax, cs:__security_cookie
0x180001831  xor     rax, rsp
0x180001834  mov     [rbp+2Fh+var_10], rax
0x180001838  mov     rax, [rbp+2Fh+arg_40]
0x18000183c  xor     r8d, r8d
0x18000183f  mov     [rbp+2Fh+var_20], rax
0x180001843  mov     r10, rdx
0x180001846  mov     rax, [rbp+2Fh+arg_38]
0x18000184a  mov     [rbp+2Fh+var_18], 4
0x180001852  lea     edx, [r8+2]
0x180001856  mov     [rbp+2Fh+var_24], r8d
0x18000185a  mov     [rbp+2Fh+var_38], rdx
0x18000185e  lea     rcx, [rax+8]
0x180001862  mov     [rbp+2Fh+var_58], rdx
0x180001866  mov     rax, [rax]
0x180001869  mov     [rbp+2Fh+var_30], rax
0x18000186d  movzx   eax, word ptr [rcx]
0x180001870  mov     [rbp+2Fh+var_28], eax
0x180001873  mov     rax, [rbp+2Fh+arg_30]
0x180001877  mov     [rbp+2Fh+var_40], rcx
0x18000187b  mov     [rbp+2Fh+var_44], r8d
0x18000187f  lea     rcx, [rax+8]
0x180001883  mov     rax, [rax]
0x180001886  mov     [rbp+2Fh+var_50], rax
0x18000188a  movzx   eax, word ptr [rcx]
0x18000188d  mov     [rbp+2Fh+var_48], eax
0x180001890  mov     rax, [rbp+2Fh+arg_28]
0x180001894  mov     [rbp+2Fh+var_60], rcx
0x180001898  mov     rcx, [rax]
0x18000189b  test    rcx, rcx
0x18000189e  jz      short loc_1800018B7
0x1800018a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800018a4  inc     rax
0x1800018a7  cmp     [rcx+rax*2], r8w
0x1800018ac  jnz     short loc_1800018A4
0x1800018ae  lea     edx, ds:2[rax*2]
0x1800018b5  jmp     short loc_1800018BE
0x1800018b7  lea     rcx, lParam
0x1800018be  mov     rax, [rbp+2Fh+arg_20]
0x1800018c2  xor     r9d, r9d
0x1800018c5  mov     [rbp+2Fh+var_80], rax
0x1800018c9  lea     rax, [rbp+2Fh+var_A0]
0x1800018cd  mov     [rbp+2Fh+var_70], rcx
0x1800018d1  lea     rcx, dword_180022000
0x1800018d8  mov     [rbp+2Fh+var_68], edx
0x1800018db  mov     rdx, r10
0x1800018de  mov     [rsp+0D0h+var_A8], rax
0x1800018e3  mov     [rsp+0D0h+var_B0], 9
0x1800018eb  mov     [rbp+2Fh+var_64], r8d
0x1800018ef  mov     [rbp+2Fh+var_78], 8
0x1800018f7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018fc  mov     rcx, [rbp+2Fh+var_10]
0x180001900  xor     rcx, rsp; StackCookie
0x180001903  call    __security_check_cookie
0x180001908  add     rsp, 0D0h
0x18000190f  pop     rbp
0x180001910  retn
```
