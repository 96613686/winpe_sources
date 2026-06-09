# PublisherConfigEnumerator::PublisherConfigEnumerator(void *)

- ea: `0x140006a30`
- end: `0x140006cc1`
- name: `??0PublisherConfigEnumerator@@QEAA@PEAX@Z`
- size: `657`
- prototype: `PublisherConfigEnumerator *__fastcall(PublisherConfigEnumerator *__hidden this, void *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000a6a0`
- `0x14000adf0`
- `0x14002e0cc`

## callees

- `0x1400039a0`
- `0x140005600`
- `0x140006a30`
- `0x140006cd0`
- `0x14000d6e8`
- `0x140018f58`
- `0x140022510`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PublisherConfigEnumerator *__fastcall PublisherConfigEnumerator::PublisherConfigEnumerator(
        PublisherConfigEnumerator *this,
        void *a2)
{
  HKEY v4; // rdi
  const char *v5; // r8
  unsigned int v6; // eax
  int v7; // edi
  PVOID *v9; // rcx
  wchar_t *v10[2]; // [rsp+28h] [rbp-29h] BYREF
  char v11; // [rsp+38h] [rbp-19h] BYREF
  void *v12[2]; // [rsp+48h] [rbp-9h] BYREF
  char v13; // [rsp+58h] [rbp+7h] BYREF
  __int16 *pExceptionObject; // [rsp+68h] [rbp+17h] BYREF
  __int64 v15; // [rsp+70h] [rbp+1Fh]
  __int64 v16; // [rsp+78h] [rbp+27h]
  int v17; // [rsp+80h] [rbp+2Fh]
  __int64 v18; // [rsp+84h] [rbp+33h]
  char v19; // [rsp+8Ch] [rbp+3Bh]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = -1;
  *((_QWORD *)this + 2) = &ValueName;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  memset_0((char *)this + 40, 0, 0x200u);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v10);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v12);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           v10,
                           qword_1400421D0,
                           (qword_1400421D8 - qword_1400421D0) >> 1)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v10,
                           L"\\Microsoft\\Windows\\CurrentVersion\\WINEVT",
                           40) )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_102b51fcdce430aa865b164defc92936_Traceguids, 14);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
        WPP_SF_d(v9[2], 10, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids, 14);
    }
    pExceptionObject = word_14003838A;
    v15 = 0;
    v16 = 0;
    v17 = 14;
    v18 = -1;
    v19 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v12[1] = v12[0];
  *(_WORD *)v12[0] = 0;
  v4 = hKey;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           v10,
                           L"\\Publishers",
                           11) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v5, 20);
    throw (EvtException *)&pExceptionObject;
  }
  v6 = RegistryKeyEnumerator::Reset((DWORD *)this, v4, v10[0], a2);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids, v6);
    }
    pExceptionObject = word_14003838A;
    v15 = 0;
    v16 = 0;
    v17 = v7;
    v18 = -1;
    v19 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( v12[0] != &v13 )
    operator delete(v12[0]);
  if ( (char *)v10[0] != &v11 )
    operator delete(v10[0]);
  return this;
}

```

## disassembly

```asm
0x140006a30  mov     rax, rsp
0x140006a33  mov     [rax+10h], rbx
0x140006a37  mov     [rax+18h], rsi
0x140006a3b  mov     [rax+8], rcx
0x140006a3f  push    rbp
0x140006a40  push    rdi
0x140006a41  push    r14
0x140006a43  lea     rbp, [rax-5Fh]
0x140006a47  sub     rsp, 90h
0x140006a4e  mov     rsi, rdx
0x140006a51  mov     rbx, rcx
0x140006a54  xor     r14d, r14d
0x140006a57  mov     [rcx], r14
0x140006a5a  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x140006a62  lea     rax, ValueName
0x140006a69  mov     [rcx+10h], rax
0x140006a6d  mov     [rcx+18h], r14
0x140006a71  mov     [rcx+20h], r14
0x140006a75  add     rcx, 28h ; '('; void *
0x140006a79  xor     edx, edx; Val
0x140006a7b  mov     r8d, 200h; Size
0x140006a81  call    memset_0
0x140006a86  nop
0x140006a87  lea     rcx, [rbp+57h+var_80]
0x140006a8b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140006a90  nop
0x140006a91  lea     rcx, [rbp+57h+var_60]
0x140006a95  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140006a9a  nop
0x140006a9b  mov     rdx, cs:qword_1400421D0
0x140006aa2  mov     r8, cs:qword_1400421D8
0x140006aa9  sub     r8, rdx
0x140006aac  sar     r8, 1
0x140006aaf  lea     rcx, [rbp+57h+var_80]
0x140006ab3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140006ab8  test    al, al
0x140006aba  jz      loc_140006C25
0x140006ac0  lea     r8d, [r14+28h]
0x140006ac4  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\CurrentVersion\\W"...
0x140006acb  lea     rcx, [rbp+57h+var_80]
0x140006acf  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140006ad4  test    al, al
0x140006ad6  jz      loc_140006C25
0x140006adc  mov     rcx, [rbp+57h+var_60]
0x140006ae0  mov     [rbp+57h+var_58], rcx
0x140006ae4  mov     [rcx], r14w
0x140006ae8  mov     rdi, cs:hKey
0x140006aef  lea     r8d, [r14+0Bh]
0x140006af3  lea     rdx, aPublishers; "\\Publishers"
0x140006afa  lea     rcx, [rbp+57h+var_80]
0x140006afe  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140006b03  test    al, al
0x140006b05  jnz     short loc_140006B62
0x140006b07  lea     rbx, WPP_GLOBAL_Control
0x140006b0e  lea     edi, [r14+0Eh]
0x140006b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b19  cmp     rcx, rbx
0x140006b1c  jz      short loc_140006B40
0x140006b1e  test    byte ptr [rcx+1Ch], 4
0x140006b22  jz      short loc_140006B40
0x140006b24  cmp     byte ptr [rcx+19h], 2
0x140006b28  jb      short loc_140006B40
0x140006b2a  lea     edx, [rdi-3]
0x140006b2d  mov     r9d, edi
0x140006b30  lea     r8, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids
0x140006b37  mov     rcx, [rcx+10h]
0x140006b3b  call    WPP_SF_d
0x140006b40  mov     r9d, 14h; int
0x140006b46  mov     edx, edi; unsigned int
0x140006b48  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140006b4c  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140006b51  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006b58  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140006b5c  call    _CxxThrowException_0
0x140006b62  mov     r9, rsi; void *
0x140006b65  mov     r8, [rbp+57h+var_80]; wchar_t *
0x140006b69  mov     rdx, rdi; HKEY
0x140006b6c  mov     rcx, rbx; this
0x140006b6f  call    ?Reset@RegistryKeyEnumerator@@QEAAJPEAUHKEY__@@PEB_WPEAX@Z; RegistryKeyEnumerator::Reset(HKEY__ *,wchar_t const *,void *)
0x140006b74  mov     edi, eax
0x140006b76  test    eax, eax
0x140006b78  jz      short loc_140006BE4
0x140006b7a  lea     rbx, WPP_GLOBAL_Control
0x140006b81  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b88  cmp     rcx, rbx
0x140006b8b  jz      short loc_140006BB1
0x140006b8d  test    byte ptr [rcx+1Ch], 4
0x140006b91  jz      short loc_140006BB1
0x140006b93  cmp     byte ptr [rcx+19h], 2
0x140006b97  jb      short loc_140006BB1
0x140006b99  mov     edx, 0Ch
0x140006b9e  mov     r9d, eax
0x140006ba1  lea     r8, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids
0x140006ba8  mov     rcx, [rcx+10h]
0x140006bac  call    WPP_SF_d
0x140006bb1  lea     rax, word_14003838A
0x140006bb8  mov     [rbp+57h+pExceptionObject], rax
0x140006bbc  mov     [rbp+57h+var_38], r14
0x140006bc0  mov     [rbp+57h+var_30], r14
0x140006bc4  mov     [rbp+57h+var_28], edi
0x140006bc7  mov     [rbp+57h+var_24], 0FFFFFFFFFFFFFFFFh
0x140006bcf  mov     [rbp+57h+var_1C], r14b
0x140006bd3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006bda  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140006bde  call    _CxxThrowException_0
0x140006be4  lea     rax, [rbp+57h+var_50]
0x140006be8  mov     rcx, [rbp+57h+var_60]; void *
0x140006bec  cmp     rcx, rax
0x140006bef  jz      short loc_140006BF7
0x140006bf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006bf6  nop
0x140006bf7  lea     rax, [rbp+57h+var_70]
0x140006bfb  mov     rcx, [rbp+57h+var_80]; void *
0x140006bff  cmp     rcx, rax
0x140006c02  jz      short loc_140006C0A
0x140006c04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006c09  nop
0x140006c0a  mov     rax, rbx
0x140006c0d  lea     r11, [rsp+0A0h+var_10]
0x140006c15  mov     rbx, [r11+28h]
0x140006c19  mov     rsi, [r11+30h]
0x140006c1d  mov     rsp, r11
0x140006c20  pop     r14
0x140006c22  pop     rdi
0x140006c23  pop     rbp
0x140006c24  retn
0x140006c25  lea     rbx, WPP_GLOBAL_Control
0x140006c2c  mov     edi, 0Eh
0x140006c31  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c38  cmp     rcx, rbx
0x140006c3b  jz      short loc_140006C8E
0x140006c3d  test    byte ptr [rcx+1Ch], 4
0x140006c41  jz      short loc_140006C65
0x140006c43  cmp     byte ptr [rcx+19h], 2
0x140006c47  jb      short loc_140006C65
0x140006c49  mov     edx, edi
0x140006c4b  mov     r9d, edi
0x140006c4e  lea     r8, WPP_102b51fcdce430aa865b164defc92936_Traceguids
0x140006c55  mov     rcx, [rcx+10h]
0x140006c59  call    WPP_SF_d
0x140006c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c65  cmp     rcx, rbx
0x140006c68  jz      short loc_140006C8E
0x140006c6a  test    byte ptr [rcx+1Ch], 4
0x140006c6e  jz      short loc_140006C8E
0x140006c70  cmp     byte ptr [rcx+19h], 2
0x140006c74  jb      short loc_140006C8E
0x140006c76  mov     edx, 0Ah
0x140006c7b  mov     r9d, edi
0x140006c7e  lea     r8, WPP_0e5f13dae36e372ed1794705a4f26032_Traceguids
0x140006c85  mov     rcx, [rcx+10h]
0x140006c89  call    WPP_SF_d
0x140006c8e  lea     rax, word_14003838A
0x140006c95  mov     [rbp+57h+pExceptionObject], rax
0x140006c99  mov     [rbp+57h+var_38], r14
0x140006c9d  mov     [rbp+57h+var_30], r14
0x140006ca1  mov     [rbp+57h+var_28], edi
0x140006ca4  mov     [rbp+57h+var_24], 0FFFFFFFFFFFFFFFFh
0x140006cac  mov     [rbp+57h+var_1C], r14b
0x140006cb0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006cb7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140006cbb  call    _CxxThrowException_0
```
