# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x180001092`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800045cc`
- `0x180004d28`
- `0x18000576c`
- `0x180005e04`

## callees

- `0x180001008`
- `0x18000131c`
- `0x1800121b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &qword_180016858;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001C008, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 78h
0x18000100c  mov     rax, cs:__security_cookie
0x180001013  xor     rax, rsp
0x180001016  mov     [rsp+78h+var_18], rax
0x18000101b  mov     rax, [rsp+78h+arg_20]
0x180001023  xor     r8d, r8d
0x180001026  mov     rcx, [rax]
0x180001029  test    rcx, rcx
0x18000102c  jz      short loc_180001045
0x18000102e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001032  inc     rax
0x180001035  cmp     [rcx+rax*2], r8w
0x18000103a  jnz     short loc_180001032
0x18000103c  lea     eax, ds:2[rax*2]
0x180001043  jmp     short loc_180001051
0x180001045  lea     rcx, qword_180016858
0x18000104c  mov     eax, 2
0x180001051  mov     [rsp+78h+var_20], eax
0x180001055  xor     r9d, r9d
0x180001058  lea     rax, [rsp+78h+var_48]
0x18000105d  mov     [rsp+78h+var_28], rcx
0x180001062  mov     [rsp+78h+var_50], rax
0x180001067  lea     rcx, dword_18001C008
0x18000106e  mov     [rsp+78h+var_58], 3
0x180001076  mov     [rsp+78h+var_1C], r8d
0x18000107b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001080  mov     rcx, [rsp+78h+var_18]
0x180001085  xor     rcx, rsp; StackCookie
0x180001088  call    __security_check_cookie
0x18000108d  add     rsp, 78h
0x180001091  retn
```
