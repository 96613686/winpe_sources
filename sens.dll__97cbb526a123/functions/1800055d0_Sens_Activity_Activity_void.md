# Sens::Activity::~Activity(void)

- ea: `0x1800055d0`
- end: `0x180005645`
- name: `??1Activity@Sens@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(Sens::Activity *this, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180004e70`
- `0x180004f10`
- `0x1800050b0`
- `0x1800051d0`

## callees

- `0x1800055d0`
- `0x180006958`
- `0x180006f9c`
- `0x180007da0`

## pseudocode

```c
void __fastcall Sens::Activity::~Activity(Sens::Activity *this, __int64 a2, __int64 a3)
{
  int v4; // [rsp+40h] [rbp+8h] BYREF
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)this = 2;
  if ( (unsigned int)dword_180011008 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180011008, a2, a3) )
  {
    v4 = *((_DWORD *)this + 10);
    v5 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180011008,
      (unsigned __int8 *)byte_18000E2BD,
      (const GUID *)((char *)this + 8),
      0,
      (__int64)&v5,
      (__int64)&v4);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hSensProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hSensProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(this);
}

```

## disassembly

```asm
0x1800055d0  push    rbx
0x1800055d2  sub     rsp, 30h
0x1800055d6  mov     dword ptr [rcx], 2
0x1800055dc  mov     rbx, rcx
0x1800055df  mov     eax, cs:dword_180011008
0x1800055e5  cmp     eax, 5
0x1800055e8  jbe     short loc_180005638
0x1800055ea  lea     rcx, dword_180011008
0x1800055f1  call    _tlgKeywordOn
0x1800055f6  test    al, al
0x1800055f8  jz      short loc_180005638
0x1800055fa  mov     eax, [rbx+28h]
0x1800055fd  lea     r8, [rbx+8]
0x180005601  mov     [rsp+38h+arg_0], eax
0x180005605  lea     rdx, byte_18000E2BD
0x18000560c  lea     rax, [rsp+38h+arg_0]
0x180005611  mov     [rsp+38h+arg_8], 1000000h
0x18000561a  mov     [rsp+38h+var_10], rax
0x18000561f  lea     rcx, dword_180011008
0x180005626  lea     rax, [rsp+38h+arg_8]
0x18000562b  xor     r9d, r9d
0x18000562e  mov     [rsp+38h+var_18], rax
0x180005633  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180005638  mov     rcx, rbx
0x18000563b  add     rsp, 30h
0x18000563f  pop     rbx
0x180005640  jmp     ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hSensProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hSensProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hSensProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
```
