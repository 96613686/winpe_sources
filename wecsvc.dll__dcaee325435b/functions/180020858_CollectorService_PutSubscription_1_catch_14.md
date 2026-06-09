# _CollectorService::PutSubscription_::_1_::catch$14

- ea: `0x180020858`
- end: `0x18002091d`
- name: `_CollectorService::PutSubscription_::_1_::catch$14`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000fb2c`
- `0x180020858`

## string_xrefs

- `0x1800208b9`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
void __fastcall __noreturn CollectorService::PutSubscription_::_1_::catch_14(__int64 a1, __int64 a2)
{
  SubscriptionManager::RetractSubscription(**(SubscriptionManager ***)(a2 + 152), *(const unsigned __int16 **)(a2 + 96));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 15080);
  }
  *(_BYTE *)(a2 + 472) = 0;
  *(_QWORD *)(a2 + 480) = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
  *(_QWORD *)(a2 + 488) = 0;
  *(_QWORD *)(a2 + 496) = 0;
  *(_DWORD *)(a2 + 504) = 15080;
  *(_DWORD *)(a2 + 508) = -1;
  *(_DWORD *)(a2 + 512) = 588;
  *(_QWORD *)(a2 + 464) = &wmi::GenericException::`vftable';
  throw (wmi::GenericException *)(a2 + 464);
}

```

## disassembly

```asm
0x180020858  mov     [rsp+arg_8], rdx
0x18002085d  push    rbp
0x18002085e  sub     rsp, 40h
0x180020862  mov     rbp, rdx
0x180020865  mov     rdx, [rbp+60h]; unsigned __int16 *
0x180020869  mov     rcx, [rbp+98h]
0x180020870  mov     rcx, [rcx]; this
0x180020873  call    ?RetractSubscription@SubscriptionManager@@QEAAXPEBG@Z; SubscriptionManager::RetractSubscription(ushort const *)
0x180020878  lea     rax, WPP_GLOBAL_Control
0x18002087f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020886  cmp     rcx, rax
0x180020889  jz      short loc_1800208B2
0x18002088b  test    byte ptr [rcx+1Ch], 10h
0x18002088f  jz      short loc_1800208B2
0x180020891  cmp     byte ptr [rcx+19h], 2
0x180020895  jb      short loc_1800208B2
0x180020897  mov     edx, 12h
0x18002089c  mov     r9d, 3AE8h
0x1800208a2  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x1800208a9  mov     rcx, [rcx+10h]
0x1800208ad  call    WPP_SF_D
0x1800208b2  mov     byte ptr [rbp+1D8h], 0
0x1800208b9  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x1800208c0  mov     [rbp+1E0h], rax
0x1800208c7  mov     qword ptr [rbp+1E8h], 0
0x1800208d2  mov     qword ptr [rbp+1F0h], 0
0x1800208dd  mov     dword ptr [rbp+1F8h], 3AE8h
0x1800208e7  mov     dword ptr [rbp+1FCh], 0FFFFFFFFh
0x1800208f1  mov     dword ptr [rbp+200h], 24Ch
0x1800208fb  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180020902  mov     [rbp+1D0h], rax
0x180020909  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180020910  lea     rcx, [rbp+1D0h]; pExceptionObject
0x180020917  call    _CxxThrowException_0
```
