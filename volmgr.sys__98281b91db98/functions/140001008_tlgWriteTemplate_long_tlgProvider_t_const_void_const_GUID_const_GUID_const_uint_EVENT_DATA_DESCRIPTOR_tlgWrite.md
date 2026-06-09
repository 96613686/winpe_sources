# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &)

- ea: `0x140001008`
- end: `0x14000118a`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@U?$_tlgWrapperByVal@$00@@U4@U4@U4@U4@U4@U4@U2@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5AEBU?$_tlgWrapperByVal@$00@@666666463@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140010d7c`

## callees

- `0x140001420`
- `0x140005050`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 *a19)
{
  __int64 v19; // rcx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int64 v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  __int64 v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  __int64 v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  __int64 v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  __int64 v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  __int64 v48; // [rsp+120h] [rbp+20h]
  __int64 v49; // [rsp+128h] [rbp+28h]
  __int64 v50; // [rsp+130h] [rbp+30h]
  __int64 v51; // [rsp+138h] [rbp+38h]

  v51 = 16;
  v49 = 1;
  v47 = 4;
  v19 = *a19;
  v48 = a18;
  v46 = a17;
  v44 = a16;
  v42 = a15;
  v40 = a14;
  v38 = a13;
  v36 = a12;
  v34 = a11;
  v32 = a10;
  v30 = a9;
  v28 = a8;
  v26 = a7;
  v50 = v19;
  v45 = 1;
  v43 = 1;
  v24 = *a6;
  v41 = 1;
  v39 = 1;
  v22 = *a5;
  v37 = 1;
  v35 = 1;
  v33 = 1;
  v31 = 8;
  v29 = 8;
  v27 = 4;
  v25 = 16;
  v23 = 16;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000A048, a2, 0, 0, 0x11u, &v21);
}

```

## disassembly

```asm
0x140001008  push    rbp
0x14000100a  lea     rbp, [rsp-50h]
0x14000100f  sub     rsp, 150h
0x140001016  mov     rax, cs:__security_cookie
0x14000101d  xor     rax, rsp
0x140001020  mov     [rbp+50h+var_10], rax
0x140001024  mov     rax, [rbp+50h+arg_90]
0x14000102b  xor     r9d, r9d
0x14000102e  xor     r8d, r8d
0x140001031  mov     [rbp+50h+var_18], 10h
0x140001039  mov     [rbp+50h+var_28], 1
0x140001041  mov     [rbp+50h+var_38], 4
0x140001049  mov     rcx, [rax]
0x14000104c  mov     rax, [rbp+50h+arg_88]
0x140001053  mov     [rbp+50h+var_30], rax
0x140001057  mov     rax, [rbp+50h+arg_80]
0x14000105e  mov     [rbp+50h+var_40], rax
0x140001062  mov     rax, [rbp+50h+arg_78]
0x140001069  mov     [rbp+50h+var_50], rax
0x14000106d  mov     rax, [rbp+50h+arg_70]
0x140001074  mov     [rbp+50h+var_60], rax
0x140001078  mov     rax, [rbp+50h+arg_68]
0x14000107f  mov     [rbp+50h+var_70], rax
0x140001083  mov     rax, [rbp+50h+arg_60]
0x14000108a  mov     [rbp+50h+var_80], rax
0x14000108e  mov     rax, [rbp+50h+arg_58]
0x140001095  mov     [rbp+50h+var_90], rax
0x140001099  mov     rax, [rbp+50h+arg_50]
0x1400010a0  mov     [rbp+50h+var_A0], rax
0x1400010a4  mov     rax, [rbp+50h+arg_48]
0x1400010ab  mov     [rbp+50h+var_B0], rax
0x1400010af  mov     rax, [rbp+50h+arg_40]
0x1400010b6  mov     [rbp+50h+var_C0], rax
0x1400010ba  mov     rax, [rbp+50h+arg_38]
0x1400010c1  mov     [rbp+50h+var_D0], rax
0x1400010c5  mov     rax, [rbp+50h+arg_30]
0x1400010cc  mov     [rsp+150h+var_E0], rax
0x1400010d1  mov     rax, [rbp+50h+arg_28]
0x1400010d8  mov     [rbp+50h+var_20], rcx
0x1400010dc  mov     [rbp+50h+var_48], 1
0x1400010e4  mov     [rbp+50h+var_58], 1
0x1400010ec  mov     rcx, [rax]
0x1400010ef  mov     rax, [rbp+50h+arg_20]
0x1400010f6  mov     [rsp+150h+var_F0], rcx
0x1400010fb  mov     [rbp+50h+var_68], 1
0x140001103  mov     [rbp+50h+var_78], 1
0x14000110b  mov     rcx, [rax]
0x14000110e  lea     rax, [rsp+150h+var_120]
0x140001113  mov     [rsp+150h+var_100], rcx
0x140001118  lea     rcx, dword_14000A048
0x14000111f  mov     [rsp+150h+var_128], rax
0x140001124  mov     [rsp+150h+var_130], 11h
0x14000112c  mov     [rbp+50h+var_88], 1
0x140001134  mov     [rbp+50h+var_98], 1
0x14000113c  mov     [rbp+50h+var_A8], 1
0x140001144  mov     [rbp+50h+var_B8], 8
0x14000114c  mov     [rbp+50h+var_C8], 8
0x140001154  mov     [rsp+150h+var_D8], 4
0x14000115d  mov     [rsp+150h+var_E8], 10h
0x140001166  mov     [rsp+150h+var_F8], 10h
0x14000116f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001174  mov     rcx, [rbp+50h+var_10]
0x140001178  xor     rcx, rsp; StackCookie
0x14000117b  call    __security_check_cookie
0x140001180  add     rsp, 150h
0x140001187  pop     rbp
0x140001188  retn
```
