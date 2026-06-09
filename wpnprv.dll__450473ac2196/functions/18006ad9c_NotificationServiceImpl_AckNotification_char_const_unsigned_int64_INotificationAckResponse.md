# NotificationServiceImpl::AckNotification(char const *,unsigned __int64,INotificationAckResponse *)

- ea: `0x18006ad9c`
- end: `0x18006aff8`
- name: `?AckNotification@NotificationServiceImpl@@AEAAJPEBD_KPEAUINotificationAckResponse@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(NotificationServiceImpl *this, const char *, __int64, struct INotificationAckResponse *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180070d10`

## callees

- `0x18000af1c`
- `0x18000fe0c`
- `0x18001c4bc`
- `0x180067574`
- `0x18006a510`
- `0x18006ad9c`
- `0x1800728e4`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strtoui64` at `0x18006af42`
- `api-ms-win-crt-private-l1-1-0!_o__strtoui64` at `0x18006af42`

## string_xrefs

- `0x18006aded`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006ae36`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006af15`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006af9e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::AckNotification(
        NotificationServiceImpl *this,
        const char *a2,
        __int64 a3,
        struct INotificationAckResponse *a4)
{
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 v11; // rbx
  int AckNotification; // eax
  __int64 v13; // r10
  int v14; // eax
  void *v15; // rcx
  const char *v16; // r9
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-B8h]
  int v19; // [rsp+20h] [rbp-B8h]
  void *v20; // [rsp+58h] [rbp-80h] BYREF
  int v21; // [rsp+60h] [rbp-78h]
  __int64 v22; // [rsp+68h] [rbp-70h] BYREF
  __int64 v23; // [rsp+70h] [rbp-68h] BYREF
  __int64 v24; // [rsp+78h] [rbp-60h]
  __int64 v25; // [rsp+80h] [rbp-58h]
  __int64 v26; // [rsp+88h] [rbp-50h]
  _QWORD v27[2]; // [rsp+90h] [rbp-48h] BYREF
  char v28; // [rsp+A0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v30; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
    v8 = (*(__int64 (**)(void))(*(_QWORD *)a4 + 24LL))();
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6EA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v8,
        v18);
    v22 = 0;
    v30 = 0;
    v9 = (*(__int64 (__fastcall **)(struct INotificationAckResponse *, __int64 *, int *))(*(_QWORD *)a4 + 40LL))(
           a4,
           &v22,
           &v30);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6EE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v9,
        v18);
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    if ( v30 )
    {
      v10 = (unsigned int)v30;
      v11 = v22;
      CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::RemoveAll(&v23);
      v23 = v11;
      v24 = v10;
      v26 = v10;
    }
    (*(void (__fastcall **)(struct INotificationAckResponse *))(*(_QWORD *)a4 + 32LL))(a4);
    v20 = 0;
    v27[0] = &v20;
    v27[1] = 0;
    v28 = 1;
    v19 = v30;
    AckNotification = WNPMessageGenerator::GenerateAckNotification(*((_QWORD *)this + 16), a3, 0, v22);
    if ( AckNotification < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)AckNotification,
        v19);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(v27);
    v21 = 0;
    v13 = _o__strtoui64(a2, 0, 16);
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int8 near **, const char *))(**((_QWORD **)this + 14)
                                                                                            + 48LL))(
            *((_QWORD *)this + 14),
            v13,
            &WNPMessageGenerator::s_AckCommand,
            "NOTIF");
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x703,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v14,
        0);
    v15 = v20;
    v20 = 0;
    if ( v15 )
      MemoryFree(v15);
    CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayStandardCompareHelper<unsigned short *>>::~CSimplePointerArray<unsigned short,CTPolicyCoTaskMem<unsigned short>,CSimpleArrayStandardCompareHelper<unsigned short *>>(&v23);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x707,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18006ad9c  mov     [rsp+arg_0], rbx
0x18006ada1  mov     [rsp+arg_8], rsi
0x18006ada6  push    rdi
0x18006ada7  push    r12
0x18006ada9  push    r13
0x18006adab  push    r14
0x18006adad  push    r15
0x18006adaf  sub     rsp, 0B0h
0x18006adb6  mov     rsi, r9
0x18006adb9  mov     r14, r8
0x18006adbc  mov     r12, rdx
0x18006adbf  mov     r15, rcx
0x18006adc2  xor     r13d, r13d
0x18006adc5  mov     [rsp+0D8h+var_88], r13d
0x18006adca  mov     rax, [r9]
0x18006adcd  lea     rdx, [rsp+0D8h+var_88]
0x18006add2  mov     rcx, r9
0x18006add5  mov     rax, [rax+18h]
0x18006add9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adde  mov     rcx, [rsp+0D8h]; this
0x18006ade6  test    eax, eax
0x18006ade8  jns     short loc_18006ADFE
0x18006adea  mov     r9d, eax; char *
0x18006aded  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006adf4  mov     edx, 6EAh; void *
0x18006adf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006adfe  mov     [rsp+0D8h+var_70], r13
0x18006ae03  mov     [rsp+0D8h+arg_18], r13d
0x18006ae0b  mov     rax, [rsi]
0x18006ae0e  lea     r8, [rsp+0D8h+arg_18]
0x18006ae16  lea     rdx, [rsp+0D8h+var_70]
0x18006ae1b  mov     rcx, rsi
0x18006ae1e  mov     rax, [rax+28h]
0x18006ae22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae27  mov     rcx, [rsp+0D8h]; this
0x18006ae2f  test    eax, eax
0x18006ae31  jns     short loc_18006AE47
0x18006ae33  mov     r9d, eax; char *
0x18006ae36  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006ae3d  mov     edx, 6EEh; void *
0x18006ae42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ae47  mov     [rsp+0D8h+var_68], r13
0x18006ae4c  mov     [rsp+0D8h+var_60], r13
0x18006ae51  mov     [rsp+0D8h+var_58], r13
0x18006ae59  mov     [rsp+0D8h+var_50], r13
0x18006ae61  mov     eax, [rsp+0D8h+arg_18]
0x18006ae68  test    eax, eax
0x18006ae6a  jz      short loc_18006AE8F
0x18006ae6c  mov     edi, eax
0x18006ae6e  mov     rbx, [rsp+0D8h+var_70]
0x18006ae73  lea     rcx, [rsp+0D8h+var_68]
0x18006ae78  call    ?RemoveAll@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXXZ; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::RemoveAll(void)
0x18006ae7d  mov     [rsp+0D8h+var_68], rbx
0x18006ae82  mov     [rsp+0D8h+var_60], rdi
0x18006ae87  mov     [rsp+0D8h+var_50], rdi
0x18006ae8f  mov     rax, [rsi]
0x18006ae92  mov     rcx, rsi
0x18006ae95  mov     rax, [rax+20h]
0x18006ae99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae9e  mov     ecx, eax
0x18006aea0  mov     [rsp+0D8h+var_80], r13
0x18006aea5  mov     [rsp+0D8h+var_84], r13d
0x18006aeaa  lea     rax, [rsp+0D8h+var_80]
0x18006aeaf  mov     [rsp+0D8h+var_48], rax
0x18006aeb7  mov     [rsp+0D8h+var_40], r13
0x18006aebf  mov     [rsp+0D8h+var_38], 1
0x18006aec7  mov     eax, [rsp+0D8h+arg_18]
0x18006aece  lea     rdx, [rsp+0D8h+var_84]
0x18006aed3  mov     [rsp+0D8h+var_A0], rdx
0x18006aed8  lea     rdx, [rsp+0D8h+var_40]
0x18006aee0  mov     [rsp+0D8h+var_A8], rdx
0x18006aee5  mov     dword ptr [rsp+0D8h+var_B0], ecx
0x18006aee9  mov     [rsp+0D8h+var_B8], eax; int
0x18006aeed  mov     r9, [rsp+0D8h+var_70]
0x18006aef2  mov     r8d, [rsp+0D8h+var_88]
0x18006aef7  mov     rdx, r14
0x18006aefa  mov     rcx, [r15+80h]
0x18006af01  call    ?GenerateAckNotification@WNPMessageGenerator@@QEAAJ_KW4__MIDL___MIDL_itf_wpntypes_0000_0000_0009@@PEAPEBGIJPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateAckNotification(unsigned __int64,__MIDL___MIDL_itf_wpntypes_0000_0000_0009,ushort const * *,uint,long,uchar * *,ulong *)
0x18006af06  mov     rcx, [rsp+0D8h]; this
0x18006af0e  test    eax, eax
0x18006af10  jns     short loc_18006AF27
0x18006af12  mov     r9d, eax; char *
0x18006af15  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006af1c  mov     edx, 6F8h; void *
0x18006af21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006af27  lea     rcx, [rsp+0D8h+var_48]
0x18006af2f  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x18006af34  mov     [rsp+0D8h+var_78], r13d
0x18006af39  xor     edx, edx
0x18006af3b  lea     r8d, [rdx+10h]
0x18006af3f  mov     rcx, r12
0x18006af42  call    cs:__imp__o__strtoui64
0x18006af48  mov     r10, rax
0x18006af4b  mov     rcx, [r15+70h]
0x18006af4f  mov     r8, [rsp+0D8h+var_80]
0x18006af54  mov     r9d, [rsp+0D8h+var_84]
0x18006af59  mov     rdx, [rcx]
0x18006af5c  mov     rax, [rdx+30h]
0x18006af60  lea     rdx, [rsp+0D8h+var_78]
0x18006af65  mov     [rsp+0D8h+var_A0], rdx
0x18006af6a  mov     [rsp+0D8h+var_A8], r14
0x18006af6f  mov     [rsp+0D8h+var_B0], r8
0x18006af74  mov     [rsp+0D8h+var_B8], r9d; int
0x18006af79  lea     r9, aNotif; "NOTIF"
0x18006af80  lea     r8, ?s_AckCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_AckCommand
0x18006af87  mov     rdx, r10
0x18006af8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af8f  mov     rcx, [rsp+0D8h]; this
0x18006af97  test    eax, eax
0x18006af99  jns     short loc_18006AFB0
0x18006af9b  mov     r9d, eax; char *
0x18006af9e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006afa5  mov     edx, 703h; void *
0x18006afaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006afb0  mov     rcx, [rsp+0D8h+var_80]; void *
0x18006afb5  mov     [rsp+0D8h+var_80], r13
0x18006afba  test    rcx, rcx
0x18006afbd  jz      short loc_18006AFC5
0x18006afbf  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006afc4  nop
0x18006afc5  lea     rcx, [rsp+0D8h+var_68]
0x18006afca  call    ??1?$CSimplePointerArray@GV?$CTPolicyCoTaskMem@G@@V?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEAA@XZ; CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayStandardCompareHelper<ushort *>>::~CSimplePointerArray<ushort,CTPolicyCoTaskMem<ushort>,CSimpleArrayStandardCompareHelper<ushort *>>(void)
0x18006afcf  xor     eax, eax
0x18006afd1  jmp     short loc_18006AFDA
0x18006afd3  mov     eax, [rsp+0D8h+arg_18]
0x18006afda  lea     r11, [rsp+0D8h+var_28]
0x18006afe2  mov     rbx, [r11+30h]
0x18006afe6  mov     rsi, [r11+38h]
0x18006afea  mov     rsp, r11
0x18006afed  pop     r15
0x18006afef  pop     r14
0x18006aff1  pop     r13
0x18006aff3  pop     r12
0x18006aff5  pop     rdi
0x18006aff6  retn
```
