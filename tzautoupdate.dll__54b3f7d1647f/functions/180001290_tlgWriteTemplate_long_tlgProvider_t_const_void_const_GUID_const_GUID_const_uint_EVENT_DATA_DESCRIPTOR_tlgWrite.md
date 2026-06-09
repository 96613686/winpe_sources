# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)

- ea: `0x180001290`
- end: `0x18000137c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a108`
- `0x18000a27c`
- `0x18000a3f0`
- `0x18000a564`
- `0x18000a6d8`
- `0x180012984`

## callees

- `0x180001290`
- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7)
{
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // ecx
  _BYTE v15[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v16; // [rsp+50h] [rbp-48h]
  __int64 v17; // [rsp+58h] [rbp-40h]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-38h]
  int v19; // [rsp+68h] [rbp-30h]
  int v20; // [rsp+6Ch] [rbp-2Ch]
  const unsigned __int16 *v21; // [rsp+70h] [rbp-28h]
  int v22; // [rsp+78h] [rbp-20h]
  int v23; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = *a7;
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v9 = &word_180021DC6;
    v11 = 1;
  }
  v22 = v11;
  v21 = v9;
  v23 = 0;
  v12 = *a6;
  if ( *a6 )
  {
    do
      ++v8;
    while ( v12[v8] );
    v13 = 2 * v8 + 2;
  }
  else
  {
    v12 = &qword_180021DC8;
    v13 = 2;
  }
  v16 = a5;
  v18 = v12;
  v19 = v13;
  v20 = 0;
  v17 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 5, v15);
}

```

## disassembly

```asm
0x180001290  sub     rsp, 98h
0x180001297  mov     rax, cs:__security_cookie
0x18000129e  xor     rax, rsp
0x1800012a1  mov     [rsp+98h+var_18], rax
0x1800012a9  mov     rax, [rsp+98h+arg_30]
0x1800012b1  mov     r10, rdx
0x1800012b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800012b8  xor     r8d, r8d
0x1800012bb  mov     rdx, [rax]
0x1800012be  test    rdx, rdx
0x1800012c1  jz      short loc_1800012D3
0x1800012c3  mov     rax, rcx
0x1800012c6  inc     rax
0x1800012c9  cmp     [rdx+rax], r8b
0x1800012cd  jnz     short loc_1800012C6
0x1800012cf  inc     eax
0x1800012d1  jmp     short loc_1800012DF
0x1800012d3  lea     rdx, word_180021DC6
0x1800012da  mov     eax, 1
0x1800012df  mov     [rsp+98h+var_20], eax
0x1800012e3  mov     rax, [rsp+98h+arg_28]
0x1800012eb  mov     [rsp+98h+var_28], rdx
0x1800012f0  mov     [rsp+98h+var_1C], r8d
0x1800012f5  mov     rdx, [rax]
0x1800012f8  test    rdx, rdx
0x1800012fb  jz      short loc_180001310
0x1800012fd  inc     rcx
0x180001300  cmp     [rdx+rcx*2], r8w
0x180001305  jnz     short loc_1800012FD
0x180001307  lea     ecx, ds:2[rcx*2]
0x18000130e  jmp     short loc_18000131C
0x180001310  lea     rdx, qword_180021DC8
0x180001317  mov     ecx, 2
0x18000131c  mov     rax, [rsp+98h+arg_20]
0x180001324  xor     r9d, r9d
0x180001327  mov     [rsp+98h+var_48], rax
0x18000132c  lea     rax, [rsp+98h+var_68]
0x180001331  mov     [rsp+98h+var_38], rdx
0x180001336  mov     rdx, r10
0x180001339  mov     [rsp+98h+var_30], ecx
0x18000133d  lea     rcx, dword_180030000
0x180001344  mov     [rsp+98h+var_70], rax
0x180001349  mov     [rsp+98h+var_78], 5
0x180001351  mov     [rsp+98h+var_2C], r8d
0x180001356  mov     [rsp+98h+var_40], 8
0x18000135f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001364  mov     rcx, [rsp+98h+var_18]
0x18000136c  xor     rcx, rsp; StackCookie
0x18000136f  call    __security_check_cookie
0x180001374  add     rsp, 98h
0x18000137b  retn
```
