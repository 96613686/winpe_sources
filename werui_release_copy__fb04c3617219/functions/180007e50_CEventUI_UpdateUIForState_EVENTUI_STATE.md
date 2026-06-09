# CEventUI::UpdateUIForState(EVENTUI_STATE)

- ea: `0x180007e50`
- end: `0x180008015`
- name: `?UpdateUIForState@CEventUI@@UEAAJW4EVENTUI_STATE@@@Z`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c80`
- `0x180006340`
- `0x180006440`
- `0x180007e50`
- `0x18000801c`
- `0x1800080d8`
- `0x1800083c0`
- `0x18000845c`
- `0x1800084b8`
- `0x180008528`
- `0x180008668`
- `0x180008f3c`
- `0x180009250`
- `0x180009580`
- `0x18000c8a0`

## import_xrefs

- `wer!WerpIsTransportAvailable` at `0x180007f6f`
- `wer!WerpIsTransportAvailable` at `0x180007f6f`
- `KERNEL32!SetEvent` at `0x180007ee2`
- `KERNEL32!SetEvent` at `0x180007ef9`
- `KERNEL32!SetEvent` at `0x180007fee`
- `KERNEL32!SetEvent` at `0x180007ee2`
- `KERNEL32!SetEvent` at `0x180007ef9`
- `KERNEL32!SetEvent` at `0x180007fee`

## pseudocode

```c
__int64 __fastcall CEventUI::UpdateUIForState(__int64 a1, int a2)
{
  int v2; // eax
  unsigned int updated; // edi
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // edx
  void *v10; // rcx
  unsigned __int16 *v11[4]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v12[5]; // [rsp+40h] [rbp-28h] BYREF

  v2 = *(_DWORD *)(a1 + 176);
  if ( v2 == 9 && a2 != 5 )
    return 0;
  if ( v2 == 1 )
  {
    if ( a2 == 1 )
    {
LABEL_27:
      if ( (unsigned int)WerpIsTransportAvailable(0, 0) )
      {
        updated = CEventUI::UpdateUIForStateQueuing((CEventUI *)a1);
      }
      else
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v12);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
        CEventUI::GetDiagosingHeaderText(a1, v12);
        UtilLoadString(v11, 350);
        updated = CEventUI::UpdateUIForStateCommon((CEventUI *)a1, v12[0], v11[0]);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v12);
      }
      v10 = *(void **)(a1 + 192);
      *(_DWORD *)(a1 + 208) = 4;
      SetEvent(v10);
      goto LABEL_31;
    }
    CEventUI::WaitForUIUptime((CEventUI *)a1);
  }
  updated = -2147467259;
  switch ( a2 )
  {
    case 1:
      goto LABEL_27;
    case 2:
      CUIDlgBase::UICallback(a1 + 8, 18);
      v9 = 0;
      v8 = 233;
      goto LABEL_26;
    case 3:
      v7 = CEventUI::UpdateUIForStateCabbingData((CEventUI *)a1);
      goto LABEL_20;
    case 4:
      v8 = 0;
      v9 = 234;
LABEL_26:
      v7 = CEventUI::UpdateUIForStateCommon((CEventUI *)a1, v9, v8);
      goto LABEL_20;
    case 5:
      updated = 0;
      if ( *(_DWORD *)(a1 + 752) )
        CEventUI::DeleteUploadNotifyIcon((CEventUI *)a1);
      break;
    case 6:
      v7 = CEventUI::UpdateUIForStateQueuing((CEventUI *)a1);
      goto LABEL_20;
    case 7:
      SetEvent(*(HANDLE *)(a1 + 192));
      v7 = CEventUI::UpdateUIForStateRecovery((CEventUI *)a1);
      goto LABEL_20;
    case 8:
      SetEvent(*(HANDLE *)(a1 + 192));
      v7 = CEventUI::UpdateUIForStateRestarting((CEventUI *)a1);
      goto LABEL_20;
    case 9:
      v7 = CEventUI::UpdateUIForStateClosing((CEventUI *)a1);
LABEL_20:
      updated = v7;
      break;
  }
LABEL_31:
  if ( *(_DWORD *)(a1 + 176) != 9 )
    *(_DWORD *)(a1 + 176) = a2;
  return updated;
}

```

## disassembly

```asm
0x180007e50  mov     [rsp+arg_0], rbx
0x180007e55  mov     [rsp+arg_8], rsi
0x180007e5a  push    rdi
0x180007e5b  sub     rsp, 60h
0x180007e5f  mov     eax, [rcx+0B0h]
0x180007e65  mov     esi, edx
0x180007e67  mov     rbx, rcx
0x180007e6a  cmp     eax, 9
0x180007e6d  jnz     short loc_180007E7B
0x180007e6f  cmp     edx, 5
0x180007e72  jz      short loc_180007E7B
0x180007e74  xor     eax, eax
0x180007e76  jmp     loc_180008005
0x180007e7b  cmp     eax, 1
0x180007e7e  jnz     short loc_180007E8D
0x180007e80  cmp     esi, eax
0x180007e82  jz      loc_180007F6B
0x180007e88  call    ?WaitForUIUptime@CEventUI@@AEAAXXZ; CEventUI::WaitForUIUptime(void)
0x180007e8d  mov     ecx, esi
0x180007e8f  mov     edi, 80004005h
0x180007e94  sub     ecx, 1
0x180007e97  jz      loc_180007F6B
0x180007e9d  sub     ecx, 1
0x180007ea0  jz      loc_180007F47
0x180007ea6  sub     ecx, 1
0x180007ea9  jz      loc_180007F3D
0x180007eaf  sub     ecx, 1
0x180007eb2  jz      short loc_180007F33
0x180007eb4  sub     ecx, 1
0x180007eb7  jz      short loc_180007F18
0x180007eb9  sub     ecx, 1
0x180007ebc  jz      short loc_180007F09
0x180007ebe  sub     ecx, 1
0x180007ec1  jz      short loc_180007EF2
0x180007ec3  sub     ecx, 1
0x180007ec6  jz      short loc_180007EDB
0x180007ec8  cmp     ecx, 1
0x180007ecb  jnz     loc_180007FF4
0x180007ed1  mov     rcx, rbx; this
0x180007ed4  call    ?UpdateUIForStateClosing@CEventUI@@AEAAJXZ; CEventUI::UpdateUIForStateClosing(void)
0x180007ed9  jmp     short loc_180007F11
0x180007edb  mov     rcx, [rbx+0C0h]; hEvent
0x180007ee2  call    cs:__imp_SetEvent
0x180007ee8  mov     rcx, rbx; this
0x180007eeb  call    ?UpdateUIForStateRestarting@CEventUI@@AEAAJXZ; CEventUI::UpdateUIForStateRestarting(void)
0x180007ef0  jmp     short loc_180007F11
0x180007ef2  mov     rcx, [rbx+0C0h]; hEvent
0x180007ef9  call    cs:__imp_SetEvent
0x180007eff  mov     rcx, rbx; this
0x180007f02  call    ?UpdateUIForStateRecovery@CEventUI@@AEAAJXZ; CEventUI::UpdateUIForStateRecovery(void)
0x180007f07  jmp     short loc_180007F11
0x180007f09  mov     rcx, rbx; this
0x180007f0c  call    ?UpdateUIForStateQueuing@CEventUI@@AEAAJXZ; CEventUI::UpdateUIForStateQueuing(void)
0x180007f11  mov     edi, eax
0x180007f13  jmp     loc_180007FF4
0x180007f18  xor     edi, edi
0x180007f1a  cmp     [rbx+2F0h], edi
0x180007f20  jz      loc_180007FF4
0x180007f26  mov     rcx, rbx; this
0x180007f29  call    ?DeleteUploadNotifyIcon@CEventUI@@AEAAJXZ; CEventUI::DeleteUploadNotifyIcon(void)
0x180007f2e  jmp     loc_180007FF4
0x180007f33  xor     r8d, r8d
0x180007f36  mov     edx, 0EAh
0x180007f3b  jmp     short loc_180007F61
0x180007f3d  mov     rcx, rbx; this
0x180007f40  call    ?UpdateUIForStateCabbingData@CEventUI@@AEAAJXZ; CEventUI::UpdateUIForStateCabbingData(void)
0x180007f45  jmp     short loc_180007F11
0x180007f47  mov     r8, [rbx+68h]
0x180007f4b  lea     rcx, [rbx+8]
0x180007f4f  mov     edx, 12h
0x180007f54  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x180007f59  xor     edx, edx; unsigned int
0x180007f5b  mov     r8d, 0E9h; unsigned int
0x180007f61  mov     rcx, rbx; this
0x180007f64  call    ?UpdateUIForStateCommon@CEventUI@@AEAAJKK@Z; CEventUI::UpdateUIForStateCommon(ulong,ulong)
0x180007f69  jmp     short loc_180007F11
0x180007f6b  xor     edx, edx
0x180007f6d  xor     ecx, ecx
0x180007f6f  call    cs:__imp_WerpIsTransportAvailable
0x180007f75  test    eax, eax
0x180007f77  jnz     short loc_180007FD3
0x180007f79  lea     rcx, [rsp+68h+var_28]; void *
0x180007f7e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180007f83  lea     rcx, [rsp+68h+var_48]; void *
0x180007f88  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180007f8d  lea     rdx, [rsp+68h+var_28]
0x180007f92  mov     rcx, rbx
0x180007f95  call    ?GetDiagosingHeaderText@CEventUI@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CEventUI::GetDiagosingHeaderText(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180007f9a  mov     edx, 15Eh
0x180007f9f  lea     rcx, [rsp+68h+var_48]
0x180007fa4  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x180007fa9  mov     r8, [rsp+68h+var_48]; unsigned __int16 *
0x180007fae  mov     rcx, rbx; this
0x180007fb1  mov     rdx, [rsp+68h+var_28]; unsigned __int16 *
0x180007fb6  call    ?UpdateUIForStateCommon@CEventUI@@AEAAJPEBG0@Z; CEventUI::UpdateUIForStateCommon(ushort const *,ushort const *)
0x180007fbb  lea     rcx, [rsp+68h+var_48]
0x180007fc0  mov     edi, eax
0x180007fc2  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180007fc7  lea     rcx, [rsp+68h+var_28]
0x180007fcc  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180007fd1  jmp     short loc_180007FDD
0x180007fd3  mov     rcx, rbx; this
0x180007fd6  call    ?UpdateUIForStateQueuing@CEventUI@@AEAAJXZ; CEventUI::UpdateUIForStateQueuing(void)
0x180007fdb  mov     edi, eax
0x180007fdd  mov     rcx, [rbx+0C0h]; hEvent
0x180007fe4  mov     dword ptr [rbx+0D0h], 4
0x180007fee  call    cs:__imp_SetEvent
0x180007ff4  cmp     dword ptr [rbx+0B0h], 9
0x180007ffb  jz      short loc_180008003
0x180007ffd  mov     [rbx+0B0h], esi
0x180008003  mov     eax, edi
0x180008005  mov     rbx, [rsp+68h+arg_0]
0x18000800a  mov     rsi, [rsp+68h+arg_8]
0x18000800f  add     rsp, 60h
0x180008013  pop     rdi
0x180008014  retn
```
