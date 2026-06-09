# DiskMonitor::DeviceNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x18006c9a0`
- end: `0x18006caf1`
- name: `?DeviceNotifyCallback@DiskMonitor@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001248`
- `0x180004d3c`
- `0x18000d560`
- `0x18001f634`
- `0x18006c148`
- `0x18006c468`
- `0x18006c9a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006caca`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006caca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006cabc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006cabc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DiskMonitor::DeviceNotifyCallback(__int64 a1, _BYTE *a2, int a3, __int64 a4, int a5)
{
  void *v8; // rbx
  __int64 v9; // rax
  DiskMonitor::WorkContext *v10; // rax
  DiskMonitor::WorkContext *v11; // rbx
  void (__stdcall *v12)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK); // rcx
  void *v13; // rbx
  __int64 v14; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  unsigned int v16; // edx
  _BYTE *v18; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v19[40]; // [rsp+48h] [rbp-28h] BYREF
  void *v20; // [rsp+98h] [rbp+28h] BYREF
  int v21; // [rsp+A0h] [rbp+30h] BYREF

  if ( (unsigned int)dword_1800BF170 > 5 )
  {
    v21 = a5;
    LODWORD(v20) = a3;
    v18 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF170,
      (unsigned int)byte_1800A92C3,
      0,
      a4,
      (__int64)&v18,
      (__int64)&v20,
      (__int64)&v21);
  }
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      if ( (unsigned int)dword_1800BF170 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1800BF170,
          byte_1800A9285,
          0,
          0);
      return 0;
    }
    v8 = operator new(0x28u);
    v20 = v8;
    v18 = v19;
    v9 = std::wstring::wstring(v19, a4 + 24);
    v10 = (DiskMonitor::WorkContext *)DiskMonitor::WorkContext::WorkContext(v8, a2, v9);
    v11 = v10;
    v12 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))DiskMonitor::RemoveDiskWorker;
  }
  else
  {
    v13 = operator new(0x28u);
    v20 = v13;
    v18 = v19;
    v14 = std::wstring::wstring(v19, a4 + 24);
    v10 = (DiskMonitor::WorkContext *)DiskMonitor::WorkContext::WorkContext(v13, a2, v14);
    v11 = v10;
    v12 = DiskMonitor::AddDiskWorker;
  }
  ThreadpoolWork = CreateThreadpoolWork(v12, v10, 0);
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else if ( v11 )
  {
    DiskMonitor::WorkContext::`scalar deleting destructor'(v11, v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18006c9a0  mov     r11, rsp
0x18006c9a3  mov     [r11+8], rbx
0x18006c9a7  push    rbp
0x18006c9a8  push    rsi
0x18006c9a9  push    rdi
0x18006c9aa  mov     rbp, rsp
0x18006c9ad  sub     rsp, 70h
0x18006c9b1  mov     rsi, r9
0x18006c9b4  mov     ebx, r8d
0x18006c9b7  mov     rdi, rdx
0x18006c9ba  mov     eax, cs:dword_1800BF170
0x18006c9c0  cmp     eax, 5
0x18006c9c3  jbe     short loc_18006CA00
0x18006c9c5  mov     eax, [rbp+arg_20]
0x18006c9c8  mov     [rbp+arg_10], eax
0x18006c9cb  mov     dword ptr [rbp+arg_8], ebx
0x18006c9ce  mov     [rbp+var_30], rdx
0x18006c9d2  lea     rax, [rbp+arg_10]
0x18006c9d6  mov     [r11-58h], rax
0x18006c9da  lea     rax, [rbp+arg_8]
0x18006c9de  mov     [r11-60h], rax
0x18006c9e2  lea     rax, [rbp+var_30]
0x18006c9e6  mov     [r11-68h], rax
0x18006c9ea  xor     r8d, r8d
0x18006c9ed  lea     rdx, byte_1800A92C3
0x18006c9f4  lea     rcx, dword_1800BF170
0x18006c9fb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006ca00  test    ebx, ebx
0x18006ca02  jz      short loc_18006CA77
0x18006ca04  cmp     ebx, 1
0x18006ca07  jz      short loc_18006CA36
0x18006ca09  mov     eax, cs:dword_1800BF170
0x18006ca0f  cmp     eax, 5
0x18006ca12  jbe     loc_18006CADF
0x18006ca18  xor     r9d, r9d
0x18006ca1b  xor     r8d, r8d
0x18006ca1e  lea     rdx, byte_1800A9285
0x18006ca25  lea     rcx, dword_1800BF170
0x18006ca2c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006ca31  jmp     loc_18006CADF
0x18006ca36  mov     ecx, 28h ; '('; Size
0x18006ca3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ca40  mov     rbx, rax
0x18006ca43  mov     [rbp+arg_8], rax
0x18006ca47  lea     rax, [rbp+var_28]
0x18006ca4b  mov     [rbp+var_30], rax
0x18006ca4f  lea     rdx, [rsi+18h]
0x18006ca53  lea     rcx, [rbp+var_28]
0x18006ca57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006ca5c  nop
0x18006ca5d  mov     r8, rax
0x18006ca60  mov     rdx, rdi
0x18006ca63  mov     rcx, rbx
0x18006ca66  call    ??0WorkContext@DiskMonitor@@QEAA@PEAV1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DiskMonitor::WorkContext::WorkContext(DiskMonitor *,std::wstring)
0x18006ca6b  mov     rbx, rax
0x18006ca6e  lea     rcx, ?RemoveDiskWorker@DiskMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; DiskMonitor::RemoveDiskWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18006ca75  jmp     short loc_18006CAB6
0x18006ca77  mov     ecx, 28h ; '('; Size
0x18006ca7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ca81  mov     rbx, rax
0x18006ca84  mov     [rbp+arg_8], rax
0x18006ca88  lea     rax, [rbp+var_28]
0x18006ca8c  mov     [rbp+var_30], rax
0x18006ca90  lea     rdx, [rsi+18h]
0x18006ca94  lea     rcx, [rbp+var_28]
0x18006ca98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006ca9d  nop
0x18006ca9e  mov     r8, rax
0x18006caa1  mov     rdx, rdi
0x18006caa4  mov     rcx, rbx
0x18006caa7  call    ??0WorkContext@DiskMonitor@@QEAA@PEAV1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DiskMonitor::WorkContext::WorkContext(DiskMonitor *,std::wstring)
0x18006caac  mov     rbx, rax
0x18006caaf  lea     rcx, ?AddDiskWorker@DiskMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006cab6  xor     r8d, r8d; pcbe
0x18006cab9  mov     rdx, rax; pv
0x18006cabc  call    cs:__imp_CreateThreadpoolWork
0x18006cac2  test    rax, rax
0x18006cac5  jz      short loc_18006CAD2
0x18006cac7  mov     rcx, rax; pwk
0x18006caca  call    cs:__imp_SubmitThreadpoolWork
0x18006cad0  jmp     short loc_18006CADF
0x18006cad2  test    rbx, rbx
0x18006cad5  jz      short loc_18006CADF
0x18006cad7  mov     rcx, rbx; this
0x18006cada  call    ??_GWorkContext@DiskMonitor@@QEAAPEAXI@Z; DiskMonitor::WorkContext::`scalar deleting destructor'(uint)
0x18006cadf  xor     eax, eax
0x18006cae1  mov     rbx, [rsp+70h+arg_0]
0x18006cae9  add     rsp, 70h
0x18006caed  pop     rdi
0x18006caee  pop     rsi
0x18006caef  pop     rbp
0x18006caf0  retn
```
