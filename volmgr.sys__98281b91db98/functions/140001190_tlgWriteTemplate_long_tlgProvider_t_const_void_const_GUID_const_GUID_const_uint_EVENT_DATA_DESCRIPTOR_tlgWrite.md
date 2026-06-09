# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x140001190`
- end: `0x140001322`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@U?$_tlgWrapperByVal@$00@@U4@U4@U4@U4@U4@U4@U2@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5AEBU?$_tlgWrapperByVal@$00@@6666664666@Z`
- size: `402`
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
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
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
        __int64 a19,
        __int64 a20)
{
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
  __int64 v52; // [rsp+140h] [rbp+40h]
  __int64 v53; // [rsp+148h] [rbp+48h]

  v52 = a20;
  v50 = a19;
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
  v53 = 1;
  v51 = 1;
  v49 = 1;
  v24 = *a6;
  v47 = 4;
  v45 = 1;
  v22 = *a5;
  v43 = 1;
  v41 = 1;
  v39 = 1;
  v37 = 1;
  v35 = 1;
  v33 = 1;
  v31 = 8;
  v29 = 8;
  v27 = 4;
  v25 = 16;
  v23 = 16;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000A048, a2, 0, 0, 0x12u, &v21);
}

```

## disassembly

```asm
0x140001190  push    rbp
0x140001192  lea     rbp, [rsp-60h]
0x140001197  sub     rsp, 160h
0x14000119e  mov     rax, cs:__security_cookie
0x1400011a5  xor     rax, rsp
0x1400011a8  mov     [rbp+60h+var_10], rax
0x1400011ac  mov     rax, [rbp+60h+arg_98]
0x1400011b3  xor     r9d, r9d
0x1400011b6  mov     [rbp+60h+var_20], rax
0x1400011ba  xor     r8d, r8d
0x1400011bd  mov     rax, [rbp+60h+arg_90]
0x1400011c4  mov     [rbp+60h+var_30], rax
0x1400011c8  mov     rax, [rbp+60h+arg_88]
0x1400011cf  mov     [rbp+60h+var_40], rax
0x1400011d3  mov     rax, [rbp+60h+arg_80]
0x1400011da  mov     [rbp+60h+var_50], rax
0x1400011de  mov     rax, [rbp+60h+arg_78]
0x1400011e5  mov     [rbp+60h+var_60], rax
0x1400011e9  mov     rax, [rbp+60h+arg_70]
0x1400011f0  mov     [rbp+60h+var_70], rax
0x1400011f4  mov     rax, [rbp+60h+arg_68]
0x1400011fb  mov     [rbp+60h+var_80], rax
0x1400011ff  mov     rax, [rbp+60h+arg_60]
0x140001206  mov     [rbp+60h+var_90], rax
0x14000120a  mov     rax, [rbp+60h+arg_58]
0x140001211  mov     [rbp+60h+var_A0], rax
0x140001215  mov     rax, [rbp+60h+arg_50]
0x14000121c  mov     [rbp+60h+var_B0], rax
0x140001220  mov     rax, [rbp+60h+arg_48]
0x140001227  mov     [rbp+60h+var_C0], rax
0x14000122b  mov     rax, [rbp+60h+arg_40]
0x140001232  mov     [rbp+60h+var_D0], rax
0x140001236  mov     rax, [rbp+60h+arg_38]
0x14000123d  mov     [rbp+60h+var_E0], rax
0x140001241  mov     rax, [rbp+60h+arg_30]
0x140001248  mov     [rsp+160h+var_F0], rax
0x14000124d  mov     rax, [rbp+60h+arg_28]
0x140001254  mov     [rbp+60h+var_18], 1
0x14000125c  mov     [rbp+60h+var_28], 1
0x140001264  mov     [rbp+60h+var_38], 1
0x14000126c  mov     rcx, [rax]
0x14000126f  mov     rax, [rbp+60h+arg_20]
0x140001276  mov     [rsp+160h+var_100], rcx
0x14000127b  mov     [rbp+60h+var_48], 4
0x140001283  mov     [rbp+60h+var_58], 1
0x14000128b  mov     rcx, [rax]
0x14000128e  lea     rax, [rsp+160h+var_130]
0x140001293  mov     [rsp+160h+var_110], rcx
0x140001298  lea     rcx, dword_14000A048
0x14000129f  mov     [rsp+160h+var_138], rax
0x1400012a4  mov     [rsp+160h+var_140], 12h
0x1400012ac  mov     [rbp+60h+var_68], 1
0x1400012b4  mov     [rbp+60h+var_78], 1
0x1400012bc  mov     [rbp+60h+var_88], 1
0x1400012c4  mov     [rbp+60h+var_98], 1
0x1400012cc  mov     [rbp+60h+var_A8], 1
0x1400012d4  mov     [rbp+60h+var_B8], 1
0x1400012dc  mov     [rbp+60h+var_C8], 8
0x1400012e4  mov     [rbp+60h+var_D8], 8
0x1400012ec  mov     [rsp+160h+var_E8], 4
0x1400012f5  mov     [rsp+160h+var_F8], 10h
0x1400012fe  mov     [rsp+160h+var_108], 10h
0x140001307  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000130c  mov     rcx, [rbp+60h+var_10]
0x140001310  xor     rcx, rsp; StackCookie
0x140001313  call    __security_check_cookie
0x140001318  add     rsp, 160h
0x14000131f  pop     rbp
0x140001320  retn
```
