# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>,>(void)

- ea: `0x14000b44c`
- end: `0x14000b581`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `309`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ccec`

## callees

- `0x14000b44c`
- `0x14001b500`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000b532`
- `KERNEL32!InitializeCriticalSection` at `0x14000b532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000b463`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x128u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 1) = v3;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_QWORD *)v3 + 16) = 0;
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 18) = 0;
  *((_DWORD *)v3 + 18) = 0;
  *(_OWORD *)(v3 + 152) = 0;
  v3[168] = 0;
  *((_WORD *)v3 + 85) = -1;
  *((_QWORD *)v3 + 22) = 0;
  *((_QWORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *(_DWORD *)(v3 + 42) = 0;
  *((_WORD *)v3 + 23) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_DWORD *)v3 + 6) = 60879299;
  *((_DWORD *)v3 + 7) = 49408;
  *((_QWORD *)v3 + 4) = "MonitorChildAccountsTipTest";
  *((_WORD *)v3 + 20) = 1;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_WORD *)v3 + 136) = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  *(_QWORD *)(v3 + 276) = 0;
  *((_DWORD *)v3 + 72) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x14000b44c  mov     [rsp+arg_0], rbx
0x14000b451  mov     [rsp+arg_8], rsi
0x14000b456  push    rdi
0x14000b457  sub     rsp, 20h
0x14000b45b  mov     rdi, rcx
0x14000b45e  mov     ecx, 128h; cb
0x14000b463  call    cs:__imp_CoTaskMemAlloc
0x14000b469  xor     esi, esi
0x14000b46b  mov     rbx, rax
0x14000b46e  test    rax, rax
0x14000b471  jz      loc_14000B57B
0x14000b477  xor     r8d, r8d
0x14000b47a  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x14000b481  mov     [rbx], rax
0x14000b484  lea     rdx, aMonitorchildac; "MonitorChildAccountsTipTest"
0x14000b48b  mov     [rbx+10h], rsi
0x14000b48f  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000b496  mov     [rbx+8], rbx
0x14000b49a  xorps   xmm0, xmm0
0x14000b49d  mov     [rbx+50h], rsi
0x14000b4a1  mov     [rbx+58h], rsi
0x14000b4a5  mov     [rbx+60h], rsi
0x14000b4a9  mov     [rbx+68h], rsi
0x14000b4ad  mov     [rbx+70h], rsi
0x14000b4b1  mov     [rbx+78h], rsi
0x14000b4b5  mov     [rbx+80h], rsi
0x14000b4bc  mov     [rbx+88h], rsi
0x14000b4c3  mov     [rbx+90h], rsi
0x14000b4ca  mov     [rbx+48h], esi
0x14000b4cd  movups  xmmword ptr [rbx+98h], xmm0
0x14000b4d4  mov     [rbx+0A8h], sil
0x14000b4db  mov     word ptr [rbx+0AAh], 0FFFFh
0x14000b4e4  mov     [rbx+0B0h], rsi
0x14000b4eb  mov     [rbx+0B8h], rsi
0x14000b4f2  mov     [rbx+0F8h], rsi
0x14000b4f9  mov     [rbx+2Ah], r8d
0x14000b4fd  mov     [rbx+2Eh], r8w
0x14000b502  mov     [rbx+0C0h], esi
0x14000b508  mov     [rbx+0F0h], esi
0x14000b50e  mov     dword ptr [rbx+18h], 3A0F1C3h
0x14000b515  mov     dword ptr [rbx+1Ch], 0C100h
0x14000b51c  mov     [rbx+20h], rdx
0x14000b520  mov     word ptr [rbx+28h], 1
0x14000b526  mov     [rbx+30h], rsi
0x14000b52a  mov     [rbx+38h], rsi
0x14000b52e  mov     [rbx+40h], rsi
0x14000b532  call    cs:__imp_InitializeCriticalSection
0x14000b538  mov     [rbx+110h], si
0x14000b53f  lea     rax, ??_7?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@6B@; const tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::`vftable'
0x14000b546  mov     [rbx], rax
0x14000b549  lea     rax, [rbx+10h]
0x14000b54d  mov     [rbx+108h], rax
0x14000b554  mov     rax, rdi
0x14000b557  mov     [rbx+114h], rsi
0x14000b55e  mov     rsi, [rsp+28h+arg_8]
0x14000b563  mov     dword ptr [rbx+120h], 1
0x14000b56d  mov     [rdi], rbx
0x14000b570  mov     rbx, [rsp+28h+arg_0]
0x14000b575  add     rsp, 20h
0x14000b579  pop     rdi
0x14000b57a  retn
0x14000b57b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
