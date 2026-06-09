# CWerComReport::_get_EventType(ushort * *)

- ea: `0x1800101bc`
- end: `0x1800102ef`
- name: `?_get_EventType@CWerComReport@@QEAAJPEAPEAG@Z`
- size: `307`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011440`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000e35c`
- `0x1800101bc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001027e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001027e`
- `OLEAUT32!__imp_SysFreeString` at `0x180010273`
- `OLEAUT32!__imp_SysFreeString` at `0x180010273`
- `wer!WerpGetEventType` at `0x180010244`
- `wer!WerpGetEventType` at `0x180010244`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_EventType(CWerComReport *this, unsigned __int16 **a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned __int16 *v8; // rax
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp+20h] BYREF

  psz = 0;
  v9 = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v9, this);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 30;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  WerApiLock = WerpGetEventType(*((_QWORD *)this + 4), &psz);
  if ( WerApiLock < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 31;
      goto LABEL_5;
    }
LABEL_6:
    if ( v9 )
      _InterlockedExchange((volatile __int32 *)(v9 + 48), 0);
    return (unsigned int)WerApiLock;
  }
  SysFreeString(*a2);
  v8 = SysAllocString(psz);
  *a2 = v8;
  if ( v8 )
  {
    if ( v9 )
      _InterlockedExchange((volatile __int32 *)(v9 + 48), 0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
    if ( v9 )
      _InterlockedExchange((volatile __int32 *)(v9 + 48), 0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800101bc  mov     rax, rsp
0x1800101bf  mov     [rax+8], rbx
0x1800101c3  mov     [rax+10h], rsi
0x1800101c7  push    rdi
0x1800101c8  sub     rsp, 20h
0x1800101cc  mov     rdi, rdx
0x1800101cf  mov     qword ptr [rax+20h], 0
0x1800101d7  mov     rdx, rcx; struct CWerComReport *
0x1800101da  mov     qword ptr [rax+18h], 0
0x1800101e2  mov     rsi, rcx
0x1800101e5  lea     rcx, [rax+18h]; this
0x1800101e9  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x1800101ee  mov     ebx, eax
0x1800101f0  test    eax, eax
0x1800101f2  jns     short loc_18001023B
0x1800101f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101fb  lea     rdx, WPP_GLOBAL_Control
0x180010202  cmp     rcx, rdx
0x180010205  jz      short loc_180010225
0x180010207  test    byte ptr [rcx+1Ch], 1
0x18001020b  jz      short loc_180010225
0x18001020d  mov     edx, 1Eh
0x180010212  mov     rcx, [rcx+10h]
0x180010216  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18001021d  mov     r9d, ebx
0x180010220  call    WPP_SF_d
0x180010225  mov     rax, [rsp+28h+arg_10]
0x18001022a  test    rax, rax
0x18001022d  jz      short loc_180010234
0x18001022f  xor     ecx, ecx
0x180010231  xchg    ecx, [rax+30h]
0x180010234  mov     eax, ebx
0x180010236  jmp     loc_1800102DF
0x18001023b  mov     rcx, [rsi+20h]
0x18001023f  lea     rdx, [rsp+28h+psz]
0x180010244  call    cs:__imp_WerpGetEventType
0x18001024a  mov     ebx, eax
0x18001024c  test    eax, eax
0x18001024e  jns     short loc_180010270
0x180010250  mov     rcx, cs:WPP_GLOBAL_Control
0x180010257  lea     rdx, WPP_GLOBAL_Control
0x18001025e  cmp     rcx, rdx
0x180010261  jz      short loc_180010225
0x180010263  test    byte ptr [rcx+1Ch], 1
0x180010267  jz      short loc_180010225
0x180010269  mov     edx, 1Fh
0x18001026e  jmp     short loc_180010212
0x180010270  mov     rcx, [rdi]; bstrString
0x180010273  call    cs:__imp_SysFreeString
0x180010279  mov     rcx, [rsp+28h+psz]; psz
0x18001027e  call    cs:__imp_SysAllocString
0x180010284  mov     [rdi], rax
0x180010287  test    rax, rax
0x18001028a  jnz     short loc_1800102CE
0x18001028c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010293  lea     rdx, WPP_GLOBAL_Control
0x18001029a  cmp     rcx, rdx
0x18001029d  jz      short loc_1800102B8
0x18001029f  test    byte ptr [rcx+1Ch], 1
0x1800102a3  jz      short loc_1800102B8
0x1800102a5  mov     rcx, [rcx+10h]
0x1800102a9  lea     edx, [rax+20h]
0x1800102ac  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800102b3  call    WPP_SF_
0x1800102b8  mov     rax, [rsp+28h+arg_10]
0x1800102bd  test    rax, rax
0x1800102c0  jz      short loc_1800102C7
0x1800102c2  xor     ecx, ecx
0x1800102c4  xchg    ecx, [rax+30h]
0x1800102c7  mov     eax, 8007000Eh
0x1800102cc  jmp     short loc_1800102DF
0x1800102ce  mov     rax, [rsp+28h+arg_10]
0x1800102d3  test    rax, rax
0x1800102d6  jz      short loc_1800102DD
0x1800102d8  xor     ecx, ecx
0x1800102da  xchg    ecx, [rax+30h]
0x1800102dd  xor     eax, eax
0x1800102df  mov     rbx, [rsp+28h+arg_0]
0x1800102e4  mov     rsi, [rsp+28h+arg_8]
0x1800102e9  add     rsp, 20h
0x1800102ed  pop     rdi
0x1800102ee  retn
```
