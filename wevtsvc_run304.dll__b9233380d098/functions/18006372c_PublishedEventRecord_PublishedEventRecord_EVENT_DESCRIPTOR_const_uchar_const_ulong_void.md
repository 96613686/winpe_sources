# PublishedEventRecord::PublishedEventRecord(_EVENT_DESCRIPTOR const &,uchar const *,ulong,void *)

- ea: `0x18006372c`
- end: `0x1800638b0`
- name: `??0PublishedEventRecord@@QEAA@AEBU_EVENT_DESCRIPTOR@@PEBEKPEAX@Z`
- size: `388`
- prototype: `PublishedEventRecord *__fastcall(PublishedEventRecord *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int8 *, unsigned int, PSID pSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180063194`
- `0x180063510`

## callees

- `0x18001b240`
- `0x18006372c`
- `0x180092008`
- `0x1800d334c`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800637fc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800637fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006379e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006379e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800637ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800637ab`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800637cb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800637cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PublishedEventRecord *__fastcall PublishedEventRecord::PublishedEventRecord(
        PublishedEventRecord *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int8 *a3,
        int a4,
        PSID pSid)
{
  unsigned __int16 LengthSid; // ax
  __int128 pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+38h] [rbp-40h]
  int v14; // [rsp+3Ch] [rbp-3Ch]
  int v15; // [rsp+40h] [rbp-38h]

  PublishedEventRecord::PublishedEventRecord(this);
  *(_QWORD *)this = &PublishedEventRecord::`vftable';
  *((_DWORD *)this + 4) = 0;
  *((_BYTE *)this + 232) = a2->Level;
  *((_WORD *)this + 118) = a2->Id;
  *((_BYTE *)this + 233) = a2->Opcode;
  *((_WORD *)this + 117) = a2->Task;
  *((_QWORD *)this + 30) = a2->Keyword;
  *((_BYTE *)this + 288) = a2->Version;
  *((_DWORD *)this + 68) = GetCurrentProcessId();
  *((_DWORD *)this + 69) = GetCurrentThreadId();
  *((_WORD *)this + 528) = a2->Channel;
  GetSystemTimePreciseAsFileTime((char *)this + 248);
  *(struct _EVENT_DESCRIPTOR *)((char *)this + 24) = *a2;
  *((_QWORD *)this + 27) = a3;
  *((_DWORD *)this + 56) = a4;
  if ( pSid )
  {
    LengthSid = GetLengthSid(pSid);
    if ( LengthSid > 0x44u )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_2d50cb38b97f398a0344401d303d916d_Traceguids, 13);
      }
      pExceptionObject = 0;
      v12 = 0;
      v13 = 13;
      v14 = -1;
      v15 = 557;
      throw (EvtException *)&pExceptionObject;
    }
    *((_WORD *)this + 223) = 19;
    *((_WORD *)this + 222) = LengthSid;
    memcpy_0((char *)this + 289, pSid, LengthSid);
  }
  return this;
}

```

## disassembly

```asm
0x18006372c  mov     [rsp+arg_0], rcx
0x180063731  push    rbx
0x180063732  push    rsi
0x180063733  push    rdi
0x180063734  push    r14
0x180063736  sub     rsp, 58h
0x18006373a  mov     esi, r9d
0x18006373d  mov     rdi, r8
0x180063740  mov     rbx, rdx
0x180063743  mov     r14, rcx
0x180063746  call    ??0PublishedEventRecord@@AEAA@XZ; PublishedEventRecord::PublishedEventRecord(void)
0x18006374b  nop
0x18006374c  lea     rax, ??_7PublishedEventRecord@@6B@; const PublishedEventRecord::`vftable'
0x180063753  mov     [r14], rax
0x180063756  mov     dword ptr [r14+10h], 0
0x18006375e  mov     al, [rbx+4]
0x180063761  mov     [r14+0E8h], al
0x180063768  movzx   eax, word ptr [rbx]
0x18006376b  mov     [r14+0ECh], ax
0x180063773  mov     al, [rbx+5]
0x180063776  mov     [r14+0E9h], al
0x18006377d  movzx   eax, word ptr [rbx+6]
0x180063781  mov     [r14+0EAh], ax
0x180063789  mov     rax, [rbx+8]
0x18006378d  mov     [r14+0F0h], rax
0x180063794  mov     al, [rbx+2]
0x180063797  mov     [r14+120h], al
0x18006379e  call    cs:__imp_GetCurrentProcessId
0x1800637a4  mov     [r14+110h], eax
0x1800637ab  call    cs:__imp_GetCurrentThreadId
0x1800637b1  mov     [r14+114h], eax
0x1800637b8  movzx   eax, byte ptr [rbx+3]
0x1800637bc  mov     [r14+420h], ax
0x1800637c4  lea     rcx, [r14+0F8h]
0x1800637cb  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800637d1  movups  xmm0, xmmword ptr [rbx]
0x1800637d4  movdqu  xmmword ptr [r14+18h], xmm0
0x1800637da  mov     [r14+0D8h], rdi
0x1800637e1  mov     [r14+0E0h], esi
0x1800637e8  mov     rbx, [rsp+78h+pSid]
0x1800637f0  test    rbx, rbx
0x1800637f3  jz      loc_1800638A3
0x1800637f9  mov     rcx, rbx; pSid
0x1800637fc  call    cs:__imp_GetLengthSid
0x180063802  cmp     ax, 44h ; 'D'
0x180063806  jbe     short loc_18006387D
0x180063808  lea     rax, WPP_GLOBAL_Control
0x18006380f  mov     ebx, 0Dh
0x180063814  mov     rcx, cs:WPP_GLOBAL_Control
0x18006381b  cmp     rcx, rax
0x18006381e  jz      short loc_180063845
0x180063820  test    dword ptr [rcx+1Ch], 10000h
0x180063827  jz      short loc_180063845
0x180063829  cmp     byte ptr [rcx+19h], 2
0x18006382d  jb      short loc_180063845
0x18006382f  lea     edx, [rbx+9]
0x180063832  mov     r9d, ebx
0x180063835  lea     r8, WPP_2d50cb38b97f398a0344401d303d916d_Traceguids
0x18006383c  mov     rcx, [rcx+10h]
0x180063840  call    WPP_SF_d
0x180063845  xorps   xmm0, xmm0
0x180063848  movdqu  [rsp+78h+pExceptionObject], xmm0
0x18006384e  mov     [rsp+78h+var_48], 0
0x180063857  mov     [rsp+78h+var_40], ebx
0x18006385b  mov     [rsp+78h+var_3C], 0FFFFFFFFh
0x180063863  mov     [rsp+78h+var_38], 22Dh
0x18006386b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180063872  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180063877  call    _CxxThrowException_0
0x18006387d  mov     word ptr [r14+1BEh], 13h
0x180063887  mov     [r14+1BCh], ax
0x18006388f  movzx   r8d, ax; Size
0x180063893  lea     rcx, [r14+121h]; void *
0x18006389a  mov     rdx, rbx; Src
0x18006389d  call    memcpy_0
0x1800638a2  nop
0x1800638a3  mov     rax, r14
0x1800638a6  add     rsp, 58h
0x1800638aa  pop     r14
0x1800638ac  pop     rdi
0x1800638ad  pop     rsi
0x1800638ae  pop     rbx
0x1800638af  retn
```
