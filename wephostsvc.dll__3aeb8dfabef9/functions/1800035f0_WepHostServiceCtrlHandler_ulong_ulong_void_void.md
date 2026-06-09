# WepHostServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800035f0`
- end: `0x1800036a3`
- name: `?WepHostServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `179`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180001e04`
- `0x180003440`
- `0x1800035f0`
- `0x1800039b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003664`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003664`

## pseudocode

```c
__int64 __fastcall WepHostServiceCtrlHandler(
        DWORD dwControl,
        __int64 dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  _QWORD *v5; // rcx
  unsigned int v6; // ebx

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_DDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      dwEventType,
      lpEventData,
      dwControl,
      dwEventType,
      lpEventData,
      lpContext);
    v5 = WPP_GLOBAL_Control;
  }
  if ( ((dwControl - 1) & 0xFFFFFFFB) == 0 )
  {
    SetEvent(hObject);
    goto LABEL_9;
  }
  if ( dwControl == 4 )
  {
    ReportSvcStatus((unsigned int)dword_18000875C, 0, 0);
LABEL_9:
    v5 = WPP_GLOBAL_Control;
    v6 = 0;
    goto LABEL_10;
  }
  v6 = 120;
LABEL_10:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_D(v5[2], 13, &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800035f0  mov     rax, rsp
0x1800035f3  mov     [rax+8], rbx
0x1800035f7  push    rdi
0x1800035f8  sub     rsp, 40h
0x1800035fc  mov     ebx, ecx
0x1800035fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003605  lea     rdi, WPP_GLOBAL_Control
0x18000360c  cmp     rcx, rdi
0x18000360f  jz      short loc_180003635
0x180003611  test    byte ptr [rcx+1Ch], 20h
0x180003615  jz      short loc_180003635
0x180003617  mov     rcx, [rcx+10h]
0x18000361b  mov     [rax-18h], r9
0x18000361f  mov     r9d, ebx
0x180003622  mov     [rax-20h], r8
0x180003626  mov     [rax-28h], edx
0x180003629  call    WPP_SF_DDqq
0x18000362e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003635  lea     eax, [rbx-1]
0x180003638  test    eax, 0FFFFFFFBh
0x18000363d  jz      short loc_18000365D
0x18000363f  cmp     ebx, 4
0x180003642  jnz     short loc_180003656
0x180003644  mov     ecx, cs:dword_18000875C
0x18000364a  xor     r8d, r8d
0x18000364d  xor     edx, edx
0x18000364f  call    ReportSvcStatus
0x180003654  jmp     short loc_18000366A
0x180003656  mov     ebx, 78h ; 'x'
0x18000365b  jmp     short loc_180003673
0x18000365d  mov     rcx, cs:hObject; hEvent
0x180003664  call    cs:__imp_SetEvent
0x18000366a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003671  xor     ebx, ebx
0x180003673  cmp     rcx, rdi
0x180003676  jz      short loc_180003696
0x180003678  test    byte ptr [rcx+1Ch], 20h
0x18000367c  jz      short loc_180003696
0x18000367e  mov     rcx, [rcx+10h]
0x180003682  lea     r8, WPP_3a1233b099da3452b07b65d2eb146164_Traceguids
0x180003689  mov     edx, 0Dh
0x18000368e  mov     r9d, ebx
0x180003691  call    WPP_SF_D
0x180003696  mov     eax, ebx
0x180003698  mov     rbx, [rsp+48h+arg_0]
0x18000369d  add     rsp, 40h
0x1800036a1  pop     rdi
0x1800036a2  retn
```
