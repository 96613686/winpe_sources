# GetChannelCommand::GetPropertyEnum(wchar_t const *,void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x1400262e4`
- end: `0x1400265d8`
- name: `?GetPropertyEnum@GetChannelCommand@@AEAAXPEB_WPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `756`
- prototype: `void(GetChannelCommand *__hidden this, const wchar_t *, void *, enum _EVT_CHANNEL_CONFIG_PROPERTY_ID)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e550`

## callees

- `0x14000a574`
- `0x140010450`
- `0x1400217b8`
- `0x140022cec`
- `0x1400262e4`
- `0x140028ce8`
- `0x140031810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetChannelCommand::GetPropertyEnum(
        GetChannelCommand *this,
        const wchar_t *a2,
        void *a3,
        EVT_CHANNEL_CONFIG_PROPERTY_ID a4)
{
  unsigned int ChannelProperty; // eax
  unsigned int v8; // r14d
  __int32 v9; // ebx
  const wchar_t *v10; // r8
  const char *v11; // [rsp+20h] [rbp-39h]
  struct _EVT_VARIANT *v12; // [rsp+40h] [rbp-19h] BYREF
  __int128 v13; // [rsp+48h] [rbp-11h] BYREF
  __int64 v14; // [rsp+58h] [rbp-1h]
  _BYTE pExceptionObject[80]; // [rsp+60h] [rbp+7h] BYREF

  v13 = 0;
  v14 = 0;
  v12 = 0;
  ChannelProperty = GetChannelProperty(a3, a4, (__int64)&v13, &v12);
  v8 = ChannelProperty;
  if ( ChannelProperty )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids,
        ChannelProperty);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v8, 0, 0, v11, 82, 4u, a2);
    throw (EvtException *)pExceptionObject;
  }
  if ( v12->Type )
  {
    if ( v12->Type != 8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, v11, 92, 4u, a2);
      throw (EvtException *)pExceptionObject;
    }
    v9 = a4 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
        goto LABEL_41;
      if ( v12->BooleanVal )
      {
        switch ( v12->BooleanVal )
        {
          case 1:
            v10 = L"Operational";
            break;
          case 2:
            v10 = L"Analytic";
            break;
          case 3:
            v10 = L"Debug";
            break;
          default:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids, 13);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, v11, 113, 4u, a2);
            throw (EvtException *)pExceptionObject;
        }
      }
      else
      {
        v10 = L"Admin";
      }
    }
    else if ( v12->BooleanVal )
    {
      if ( v12->BooleanVal )
      {
        v10 = L"System";
      }
      else
      {
        if ( v12->BooleanVal != 2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids, 13);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, 0, 0, v11, 129, 4u, a2);
          throw (EvtException *)pExceptionObject;
        }
        v10 = L"Custom";
      }
    }
    else
    {
      v10 = L"Application";
    }
    XmlPrinter::PrintNameValue((GetChannelCommand *)((char *)this + 72), a2, v10);
  }
LABEL_41:
  if ( (_QWORD)v13 )
    std::_Deallocate<16>(v13, v14 - v13);
}

```

## disassembly

```asm
0x1400262e4  push    rbp
0x1400262e6  push    rbx
0x1400262e7  push    rsi
0x1400262e8  push    rdi
0x1400262e9  push    r14
0x1400262eb  lea     rbp, [rsp-37h]
0x1400262f0  sub     rsp, 90h
0x1400262f7  mov     ebx, r9d
0x1400262fa  mov     rax, r8
0x1400262fd  mov     rdi, rdx
0x140026300  mov     rsi, rcx
0x140026303  xorps   xmm0, xmm0
0x140026306  movdqu  [rbp+57h+var_68], xmm0
0x14002630b  mov     [rbp+57h+var_58], 0
0x140026313  mov     [rbp+57h+var_70], 0
0x14002631b  lea     r9, [rbp+57h+var_70]
0x14002631f  lea     r8, [rbp+57h+var_68]
0x140026323  mov     edx, ebx; PropertyId
0x140026325  mov     rcx, rax; ChannelConfig
0x140026328  call    ?GetChannelProperty@@YAKPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x14002632d  mov     r14d, eax
0x140026330  test    eax, eax
0x140026332  jz      short loc_1400263A8
0x140026334  lea     rcx, WPP_GLOBAL_Control
0x14002633b  mov     r10, cs:WPP_GLOBAL_Control
0x140026342  cmp     r10, rcx
0x140026345  jz      short loc_140026370
0x140026347  test    dword ptr [r10+1Ch], 400000h
0x14002634f  jz      short loc_140026370
0x140026351  cmp     byte ptr [r10+19h], 2
0x140026356  jb      short loc_140026370
0x140026358  mov     edx, 0Ch
0x14002635d  mov     r9d, eax
0x140026360  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x140026367  mov     rcx, [r10+10h]
0x14002636b  call    WPP_SF_d
0x140026370  mov     [rsp+0B0h+Src], rdi; Src
0x140026375  mov     [rsp+0B0h+var_80], 4; unsigned int
0x14002637d  mov     [rsp+0B0h+var_88], 52h ; 'R'; int
0x140026385  xor     r9d, r9d; unsigned int
0x140026388  xor     r8d, r8d; unsigned int
0x14002638b  mov     edx, r14d; unsigned int
0x14002638e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140026392  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026397  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002639e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400263a2  call    _CxxThrowException_0
0x1400263a8  mov     rcx, [rbp+57h+var_70]
0x1400263ac  cmp     dword ptr [rcx+0Ch], 0
0x1400263b0  jz      loc_1400265B5
0x1400263b6  cmp     dword ptr [rcx+0Ch], 8
0x1400263ba  jz      short loc_14002642F
0x1400263bc  lea     rcx, WPP_GLOBAL_Control
0x1400263c3  mov     ebx, 0Dh
0x1400263c8  mov     rax, cs:WPP_GLOBAL_Control
0x1400263cf  cmp     rax, rcx
0x1400263d2  jz      short loc_1400263F8
0x1400263d4  test    dword ptr [rax+1Ch], 400000h
0x1400263db  jz      short loc_1400263F8
0x1400263dd  cmp     byte ptr [rax+19h], 2
0x1400263e1  jb      short loc_1400263F8
0x1400263e3  mov     edx, ebx
0x1400263e5  mov     r9d, ebx
0x1400263e8  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x1400263ef  mov     rcx, [rax+10h]
0x1400263f3  call    WPP_SF_d
0x1400263f8  mov     [rsp+0B0h+Src], rdi; Src
0x1400263fd  mov     [rsp+0B0h+var_80], 4; unsigned int
0x140026405  mov     [rsp+0B0h+var_88], 5Ch ; '\'; int
0x14002640d  xor     r9d, r9d; unsigned int
0x140026410  xor     r8d, r8d; unsigned int
0x140026413  mov     edx, ebx; unsigned int
0x140026415  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140026419  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14002641e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026425  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140026429  call    _CxxThrowException_0
0x14002642f  sub     ebx, 1
0x140026432  jz      loc_140026503
0x140026438  cmp     ebx, 1
0x14002643b  jnz     loc_1400265B5
0x140026441  mov     ecx, [rcx]
0x140026443  test    ecx, ecx
0x140026445  jz      loc_1400264F7
0x14002644b  sub     ecx, ebx
0x14002644d  jz      loc_1400264EB
0x140026453  sub     ecx, ebx
0x140026455  jz      loc_1400264DF
0x14002645b  cmp     ecx, ebx
0x14002645d  jz      short loc_1400264D3
0x14002645f  lea     rcx, WPP_GLOBAL_Control
0x140026466  mov     ebx, 0Dh
0x14002646b  mov     rax, cs:WPP_GLOBAL_Control
0x140026472  cmp     rax, rcx
0x140026475  jz      short loc_14002649C
0x140026477  test    dword ptr [rax+1Ch], 400000h
0x14002647e  jz      short loc_14002649C
0x140026480  cmp     byte ptr [rax+19h], 2
0x140026484  jb      short loc_14002649C
0x140026486  lea     edx, [rbx+1]
0x140026489  mov     r9d, ebx
0x14002648c  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x140026493  mov     rcx, [rax+10h]
0x140026497  call    WPP_SF_d
0x14002649c  mov     [rsp+0B0h+Src], rdi; Src
0x1400264a1  mov     [rsp+0B0h+var_80], 4; unsigned int
0x1400264a9  mov     [rsp+0B0h+var_88], 71h ; 'q'; int
0x1400264b1  xor     r9d, r9d; unsigned int
0x1400264b4  xor     r8d, r8d; unsigned int
0x1400264b7  mov     edx, ebx; unsigned int
0x1400264b9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400264bd  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400264c2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400264c9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400264cd  call    _CxxThrowException_0
0x1400264d3  lea     r8, aDebug; "Debug"
0x1400264da  jmp     loc_1400265A8
0x1400264df  lea     r8, aAnalytic; "Analytic"
0x1400264e6  jmp     loc_1400265A8
0x1400264eb  lea     r8, aOperational; "Operational"
0x1400264f2  jmp     loc_1400265A8
0x1400264f7  lea     r8, aAdmin; "Admin"
0x1400264fe  jmp     loc_1400265A8
0x140026503  mov     ecx, [rcx]
0x140026505  test    ecx, ecx
0x140026507  jz      loc_1400265A1
0x14002650d  sub     ecx, 1
0x140026510  jz      loc_140026598
0x140026516  cmp     ecx, 1
0x140026519  jz      short loc_14002658F
0x14002651b  lea     rcx, WPP_GLOBAL_Control
0x140026522  mov     ebx, 0Dh
0x140026527  mov     rax, cs:WPP_GLOBAL_Control
0x14002652e  cmp     rax, rcx
0x140026531  jz      short loc_140026558
0x140026533  test    dword ptr [rax+1Ch], 400000h
0x14002653a  jz      short loc_140026558
0x14002653c  cmp     byte ptr [rax+19h], 2
0x140026540  jb      short loc_140026558
0x140026542  lea     edx, [rbx+2]
0x140026545  mov     r9d, ebx
0x140026548  lea     r8, WPP_44bc6a6d212939c8da91f29f7061dc3b_Traceguids
0x14002654f  mov     rcx, [rax+10h]
0x140026553  call    WPP_SF_d
0x140026558  mov     [rsp+0B0h+Src], rdi; Src
0x14002655d  mov     [rsp+0B0h+var_80], 4; unsigned int
0x140026565  mov     [rsp+0B0h+var_88], 81h; int
0x14002656d  xor     r9d, r9d; unsigned int
0x140026570  xor     r8d, r8d; unsigned int
0x140026573  mov     edx, ebx; unsigned int
0x140026575  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140026579  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14002657e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026585  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140026589  call    _CxxThrowException_0
0x14002658f  lea     r8, String2; "Custom"
0x140026596  jmp     short loc_1400265A8
0x140026598  lea     r8, aSystem; "System"
0x14002659f  jmp     short loc_1400265A8
0x1400265a1  lea     r8, aApplication; "Application"
0x1400265a8  mov     rdx, rdi; wchar_t *
0x1400265ab  lea     rcx, [rsi+48h]; this
0x1400265af  call    ?PrintNameValue@XmlPrinter@@QEAAXPEB_W0@Z; XmlPrinter::PrintNameValue(wchar_t const *,wchar_t const *)
0x1400265b4  nop
0x1400265b5  mov     rcx, qword ptr [rbp+57h+var_68]
0x1400265b9  test    rcx, rcx
0x1400265bc  jz      short loc_1400265CA
0x1400265be  mov     rdx, [rbp+57h+var_58]
0x1400265c2  sub     rdx, rcx
0x1400265c5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400265ca  add     rsp, 90h
0x1400265d1  pop     r14
0x1400265d3  pop     rdi
0x1400265d4  pop     rsi
0x1400265d5  pop     rbx
0x1400265d6  pop     rbp
0x1400265d7  retn
```
