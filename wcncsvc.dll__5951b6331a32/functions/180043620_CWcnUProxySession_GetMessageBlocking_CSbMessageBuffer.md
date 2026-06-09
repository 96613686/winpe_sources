# CWcnUProxySession::GetMessageBlocking(CSbMessageBuffer *)

- ea: `0x180043620`
- end: `0x1800437bc`
- name: `?GetMessageBlocking@CWcnUProxySession@@UEAAJPEAVCSbMessageBuffer@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CWcnUProxySession *this, struct CSbMessageBuffer *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a74c`
- `0x180043620`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043715`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043715`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180043764`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180043764`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800436c2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800436c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004376e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004376e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436ec`

## string_xrefs

- `0x18004368c`: `pIncomingMessage`

## pseudocode

```c
__int64 __fastcall CWcnUProxySession::GetMessageBlocking(CWcnUProxySession *this, struct CSbMessageBuffer *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  DWORD v8; // eax
  DWORD v9; // eax
  unsigned int LastError; // ebx
  signed int v11; // ebx
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // r10

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 19, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v8 = WaitForMultipleObjectsEx(2u, (const HANDLE *)this + 3, 0, 0x7530u, 0);
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 == 257 )
        {
          v11 = -2147023436;
        }
        else
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0x80070000;
          else
            LastError = GetLastError();
          v11 = LastError | 0x80000000;
        }
      }
      else
      {
        v11 = -2147023673;
      }
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      *((_OWORD *)a2 + 2) = *(_OWORD *)((char *)this + 72);
      v12 = CSbSafeBuffer::CopyFromBuffer(a2, (CWcnUProxySession *)((char *)this + 40));
      v11 = v12;
      if ( v12 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids,
          (unsigned int)v12);
      ResetEvent(*((HANDLE *)this + 3));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
    {
      v13 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v14 + 16), 22, (unsigned int)WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v13, v11);
    }
    return (unsigned int)v11;
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 20, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, "pIncomingMessage");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180043620  push    rbx
0x180043622  push    rbp
0x180043623  push    rsi
0x180043624  push    rdi
0x180043625  push    r14
0x180043627  sub     rsp, 30h
0x18004362b  mov     rbx, rdx
0x18004362e  mov     rdi, rcx
0x180043631  mov     r10, cs:WPP_GLOBAL_Control
0x180043638  lea     r14, WPP_GLOBAL_Control
0x18004363f  cmp     r10, r14
0x180043642  jz      short loc_180043674
0x180043644  cmp     byte ptr [r10+19h], 6
0x180043649  jb      short loc_180043674
0x18004364b  mov     ecx, 1; int
0x180043650  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180043655  mov     rcx, [r10+10h]
0x180043659  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180043660  mov     edx, 13h
0x180043665  mov     r9, rax
0x180043668  call    WPP_SF_s
0x18004366d  mov     r10, cs:WPP_GLOBAL_Control
0x180043674  test    rbx, rbx
0x180043677  jnz     short loc_1800436A9
0x180043679  cmp     r10, r14
0x18004367c  jz      short loc_18004369F
0x18004367e  cmp     byte ptr [r10+19h], 2
0x180043683  jb      short loc_18004369F
0x180043685  mov     rcx, [r10+10h]
0x180043689  lea     edx, [rbx+14h]
0x18004368c  lea     r9, aPincomingmessa; "pIncomingMessage"
0x180043693  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x18004369a  call    WPP_SF_s
0x18004369f  mov     eax, 80004003h
0x1800436a4  jmp     loc_1800437B1
0x1800436a9  xor     r8d, r8d; bWaitAll
0x1800436ac  mov     [rsp+58h+bAlertable], 0; bAlertable
0x1800436b4  mov     r9d, 7530h; dwMilliseconds
0x1800436ba  lea     rdx, [rdi+18h]; lpHandles
0x1800436be  lea     ecx, [r8+2]; nCount
0x1800436c2  call    cs:__imp_WaitForMultipleObjectsEx
0x1800436c8  test    eax, eax
0x1800436ca  jz      short loc_180043711
0x1800436cc  sub     eax, 1
0x1800436cf  jz      short loc_18004370A
0x1800436d1  cmp     eax, 101h
0x1800436d6  jz      short loc_180043703
0x1800436d8  call    cs:__imp_GetLastError
0x1800436de  test    eax, eax
0x1800436e0  jg      short loc_1800436EC
0x1800436e2  call    cs:__imp_GetLastError
0x1800436e8  mov     ebx, eax
0x1800436ea  jmp     short loc_1800436FB
0x1800436ec  call    cs:__imp_GetLastError
0x1800436f2  movzx   ebx, ax
0x1800436f5  or      ebx, 80070000h
0x1800436fb  or      ebx, 80000000h
0x180043701  jmp     short loc_180043774
0x180043703  mov     ebx, 800705B4h
0x180043708  jmp     short loc_180043774
0x18004370a  mov     ebx, 800704C7h
0x18004370f  jmp     short loc_180043774
0x180043711  lea     rcx, [rdi+58h]; lpCriticalSection
0x180043715  call    cs:__imp_EnterCriticalSection
0x18004371b  lea     rdx, [rdi+28h]; struct CSbSafeBuffer *
0x18004371f  mov     rcx, rbx; this
0x180043722  movups  xmm0, xmmword ptr [rdx+20h]
0x180043726  movdqu  xmmword ptr [rbx+20h], xmm0
0x18004372b  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBV1@@Z; CSbSafeBuffer::CopyFromBuffer(CSbSafeBuffer const *)
0x180043730  mov     ebx, eax
0x180043732  test    eax, eax
0x180043734  jns     short loc_180043760
0x180043736  mov     rcx, cs:WPP_GLOBAL_Control
0x18004373d  cmp     rcx, r14
0x180043740  jz      short loc_180043760
0x180043742  cmp     byte ptr [rcx+19h], 3
0x180043746  jb      short loc_180043760
0x180043748  mov     rcx, [rcx+10h]
0x18004374c  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180043753  mov     edx, 15h
0x180043758  mov     r9d, eax
0x18004375b  call    WPP_SF_d
0x180043760  mov     rcx, [rdi+18h]; hEvent
0x180043764  call    cs:__imp_ResetEvent
0x18004376a  lea     rcx, [rdi+58h]; lpCriticalSection
0x18004376e  call    cs:__imp_LeaveCriticalSection
0x180043774  mov     r10, cs:WPP_GLOBAL_Control
0x18004377b  cmp     r10, r14
0x18004377e  jz      short loc_1800437AF
0x180043780  test    ebx, ebx
0x180043782  js      short loc_18004378B
0x180043784  cmp     byte ptr [r10+19h], 6
0x180043789  jb      short loc_1800437AF
0x18004378b  or      ecx, 0FFFFFFFFh; int
0x18004378e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180043793  mov     rcx, [r10+10h]
0x180043797  lea     r8, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x18004379e  mov     edx, 16h
0x1800437a3  mov     [rsp+58h+bAlertable], ebx
0x1800437a7  mov     r9, rax
0x1800437aa  call    WPP_SF_sd
0x1800437af  mov     eax, ebx
0x1800437b1  add     rsp, 30h
0x1800437b5  pop     r14
0x1800437b7  pop     rdi
0x1800437b8  pop     rsi
0x1800437b9  pop     rbp
0x1800437ba  pop     rbx
0x1800437bb  retn
```
