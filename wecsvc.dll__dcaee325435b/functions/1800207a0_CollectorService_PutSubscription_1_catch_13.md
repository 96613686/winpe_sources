# _CollectorService::PutSubscription_::_1_::catch$13

- ea: `0x1800207a0`
- end: `0x180020852`
- name: `_CollectorService::PutSubscription_::_1_::catch$13`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800207a0`

## string_xrefs

- `0x1800207ee`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
void __fastcall __noreturn CollectorService::PutSubscription_::_1_::catch_13(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 15080);
  }
  *(_BYTE *)(a2 + 416) = 0;
  *(_QWORD *)(a2 + 424) = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
  *(_QWORD *)(a2 + 432) = 0;
  *(_QWORD *)(a2 + 440) = 0;
  *(_DWORD *)(a2 + 448) = 15080;
  *(_DWORD *)(a2 + 452) = -1;
  *(_DWORD *)(a2 + 456) = 618;
  *(_QWORD *)(a2 + 408) = &wmi::GenericException::`vftable';
  throw (wmi::GenericException *)(a2 + 408);
}

```

## disassembly

```asm
0x1800207a0  mov     [rsp+arg_8], rdx
0x1800207a5  push    rbp
0x1800207a6  sub     rsp, 40h
0x1800207aa  mov     rbp, rdx
0x1800207ad  lea     rax, WPP_GLOBAL_Control
0x1800207b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207bb  cmp     rcx, rax
0x1800207be  jz      short loc_1800207E7
0x1800207c0  test    byte ptr [rcx+1Ch], 10h
0x1800207c4  jz      short loc_1800207E7
0x1800207c6  cmp     byte ptr [rcx+19h], 2
0x1800207ca  jb      short loc_1800207E7
0x1800207cc  mov     edx, 13h
0x1800207d1  mov     r9d, 3AE8h
0x1800207d7  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x1800207de  mov     rcx, [rcx+10h]
0x1800207e2  call    WPP_SF_D
0x1800207e7  mov     byte ptr [rbp+1A0h], 0
0x1800207ee  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x1800207f5  mov     [rbp+1A8h], rax
0x1800207fc  mov     qword ptr [rbp+1B0h], 0
0x180020807  mov     qword ptr [rbp+1B8h], 0
0x180020812  mov     dword ptr [rbp+1C0h], 3AE8h
0x18002081c  mov     dword ptr [rbp+1C4h], 0FFFFFFFFh
0x180020826  mov     dword ptr [rbp+1C8h], 26Ah
0x180020830  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180020837  mov     [rbp+198h], rax
0x18002083e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180020845  lea     rcx, [rbp+198h]; pExceptionObject
0x18002084c  call    _CxxThrowException_0
```
