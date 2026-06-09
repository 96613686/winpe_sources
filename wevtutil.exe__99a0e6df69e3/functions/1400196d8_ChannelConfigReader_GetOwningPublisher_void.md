# ChannelConfigReader::GetOwningPublisher(void)

- ea: `0x1400196d8`
- end: `0x1400197ad`
- name: `?GetOwningPublisher@ChannelConfigReader@@QEBA?AU_GUID@@XZ`
- size: `213`
- prototype: `struct _GUID *__fastcall(ChannelConfigReader *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1400073ec`

## callees

- `0x1400039a0`
- `0x140004ae0`
- `0x140005600`
- `0x140005620`
- `0x1400196d8`
- `0x140022cec`
- `0x14002a328`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _GUID *__fastcall ChannelConfigReader::GetOwningPublisher(
        ChannelConfigReader *this,
        struct _GUID *__return_ptr retstr)
{
  HKEY *v3; // r10
  int StringValueNoThrow; // eax
  const char *v5; // r8
  void *v7[2]; // [rsp+20h] [rbp-58h] BYREF
  char v8; // [rsp+30h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v7);
  StringValueNoThrow = RegReadStringValueNoThrow(*v3, 0, L"OwningPublisher", (__int64)v7);
  *retstr = 0;
  if ( StringValueNoThrow == 2 )
  {
    if ( v7[0] != &v8 )
      operator delete(v7[0]);
  }
  else
  {
    if ( !tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(retstr, v7) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v5, 231);
      throw (EvtException *)pExceptionObject;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v7);
  }
  return retstr;
}

```

## disassembly

```asm
0x1400196d8  push    rbx
0x1400196da  sub     rsp, 70h
0x1400196de  mov     rbx, rdx
0x1400196e1  mov     r10, rcx
0x1400196e4  lea     rcx, [rsp+78h+var_58]
0x1400196e9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400196ee  nop
0x1400196ef  lea     r9, [rsp+78h+var_58]
0x1400196f4  lea     r8, aOwningpublishe; "OwningPublisher"
0x1400196fb  xor     edx, edx
0x1400196fd  mov     rcx, [r10]; hKey
0x140019700  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140019705  xorps   xmm0, xmm0
0x140019708  movups  xmmword ptr [rbx], xmm0
0x14001970b  cmp     eax, 2
0x14001970e  jnz     short loc_14001972A
0x140019710  lea     rax, [rsp+78h+var_48]
0x140019715  mov     rcx, [rsp+78h+var_58]; void *
0x14001971a  cmp     rcx, rax
0x14001971d  jz      loc_1400197A4
0x140019723  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140019728  jmp     short loc_1400197A4
0x14001972a  lea     rdx, [rsp+78h+var_58]
0x14001972f  mov     rcx, rbx
0x140019732  call    ??$string_to_guid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(_GUID *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x140019737  test    rax, rax
0x14001973a  jnz     short loc_14001979A
0x14001973c  lea     rax, WPP_GLOBAL_Control
0x140019743  mov     ebx, 0Dh
0x140019748  mov     rcx, cs:WPP_GLOBAL_Control
0x14001974f  cmp     rcx, rax
0x140019752  jz      short loc_140019776
0x140019754  test    byte ptr [rcx+1Ch], 4
0x140019758  jz      short loc_140019776
0x14001975a  cmp     byte ptr [rcx+19h], 2
0x14001975e  jb      short loc_140019776
0x140019760  lea     edx, [rbx+11h]
0x140019763  mov     r9d, ebx
0x140019766  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x14001976d  mov     rcx, [rcx+10h]
0x140019771  call    WPP_SF_d
0x140019776  mov     r9d, 0E7h; int
0x14001977c  mov     edx, ebx; unsigned int
0x14001977e  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140019783  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140019788  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001978f  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140019794  call    _CxxThrowException_0
0x14001979a  lea     rcx, [rsp+78h+var_58]
0x14001979f  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400197a4  mov     rax, rbx
0x1400197a7  add     rsp, 70h
0x1400197ab  pop     rbx
0x1400197ac  retn
```
