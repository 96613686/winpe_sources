# CServerHandler::ConnectedAndLogedOn(void)

- ea: `0x180040150`
- end: `0x180040248`
- name: `?ConnectedAndLogedOn@CServerHandler@@QEAAJXZ`
- size: `248`
- prototype: `__int64 __fastcall(CServerHandler *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040330`
- `0x180040790`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x180040150`
- `0x1800411e8`
- `0x1800412a0`
- `0x180041850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004016a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004016a`

## string_xrefs

- `0x1800401b3`: `OpenChannel failed`

## pseudocode

```c
__int64 __fastcall CServerHandler::ConnectedAndLogedOn(CServerHandler *this)
{
  int v2; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v4; // edx
  const char *v5; // rcx

  if ( *((_DWORD *)this + 20) && *((_QWORD *)this + 9) )
    GetCurrentThreadId();
  v2 = CServerHandler::OpenChannel(this);
  if ( v2 >= 0 )
  {
    v2 = CCommonPNPPDUHandler::SendVersion((CServerHandler *)((char *)this + 64));
    if ( !v2 || (CServerHandler::ProtocolError(this, 4), v2 >= 0) )
    {
      *((_DWORD *)this + 32) = 1;
      return (unsigned int)v2;
    }
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 17;
      v5 = "SendVersion FAILED";
      goto LABEL_9;
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = 16;
    v5 = "OpenChannel failed";
LABEL_9:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v4,
      (unsigned int)WPP_f70cd3a88afa3710197e4c5386561e98_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v5,
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180040150  mov     [rsp+arg_0], rbx
0x180040155  push    rdi
0x180040156  sub     rsp, 30h
0x18004015a  cmp     dword ptr [rcx+50h], 0
0x18004015e  mov     rbx, rcx
0x180040161  jz      short loc_180040170
0x180040163  cmp     qword ptr [rcx+48h], 0
0x180040168  jz      short loc_180040170
0x18004016a  call    cs:__imp_GetCurrentThreadId
0x180040170  mov     rcx, rbx; this
0x180040173  call    ?OpenChannel@CServerHandler@@AEAAJXZ; CServerHandler::OpenChannel(void)
0x180040178  mov     edi, eax
0x18004017a  test    eax, eax
0x18004017c  jns     short loc_1800401DF
0x18004017e  mov     rax, cs:WPP_GLOBAL_Control
0x180040185  lea     rcx, WPP_GLOBAL_Control
0x18004018c  cmp     rax, rcx
0x18004018f  jz      loc_18004023B
0x180040195  test    byte ptr [rax+1Ch], 8
0x180040199  jz      loc_18004023B
0x18004019f  cmp     byte ptr [rax+19h], 2
0x1800401a3  jb      loc_18004023B
0x1800401a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800401ae  mov     edx, 10h
0x1800401b3  lea     rcx, aOpenchannelFai; "OpenChannel failed"
0x1800401ba  mov     [rsp+38h+var_10], edi
0x1800401be  lea     r8, WPP_f70cd3a88afa3710197e4c5386561e98_Traceguids
0x1800401c5  mov     [rsp+38h+var_18], rcx
0x1800401ca  mov     r9d, eax
0x1800401cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800401d4  mov     rcx, [rcx+10h]
0x1800401d8  call    WPP_SF_DsD
0x1800401dd  jmp     short loc_18004023B
0x1800401df  lea     rcx, [rbx+40h]; this
0x1800401e3  call    ?SendVersion@CCommonPNPPDUHandler@@MEAAJXZ; CCommonPNPPDUHandler::SendVersion(void)
0x1800401e8  mov     edi, eax
0x1800401ea  test    eax, eax
0x1800401ec  jz      short loc_180040231
0x1800401ee  mov     edx, 4
0x1800401f3  mov     rcx, rbx
0x1800401f6  call    ?ProtocolError@CServerHandler@@AEAAXW4EProtocolError@1@@Z; CServerHandler::ProtocolError(CServerHandler::EProtocolError)
0x1800401fb  test    edi, edi
0x1800401fd  jns     short loc_180040231
0x1800401ff  mov     rax, cs:WPP_GLOBAL_Control
0x180040206  lea     rcx, WPP_GLOBAL_Control
0x18004020d  cmp     rax, rcx
0x180040210  jz      short loc_18004023B
0x180040212  test    byte ptr [rax+1Ch], 8
0x180040216  jz      short loc_18004023B
0x180040218  cmp     byte ptr [rax+19h], 2
0x18004021c  jb      short loc_18004023B
0x18004021e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040223  mov     edx, 11h
0x180040228  lea     rcx, aSendversionFai; "SendVersion FAILED"
0x18004022f  jmp     short loc_1800401BA
0x180040231  mov     dword ptr [rbx+80h], 1
0x18004023b  mov     rbx, [rsp+38h+arg_0]
0x180040240  mov     eax, edi
0x180040242  add     rsp, 30h
0x180040246  pop     rdi
0x180040247  retn
```
