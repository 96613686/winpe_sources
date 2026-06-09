# FastWppTraceMessage

- ea: `0x18006b58c`
- end: `0x18006b728`
- name: `FastWppTraceMessage`
- size: `412`
- prototype: ``
- caller_count: `141`
- callee_count: `3`
- tags: ``

## callers

- `0x180092008`
- `0x18009205c`
- `0x1800920e4`
- `0x18009218c`
- `0x1800921ec`
- `0x180092260`
- `0x1800922d4`
- `0x18009234c`
- `0x1800923bc`
- `0x180092428`
- `0x180092498`
- `0x180092500`
- `0x180092564`
- `0x180092578`
- `0x180092614`
- `0x18009267c`
- `0x1800926dc`
- `0x180092780`
- `0x1800927cc`
- `0x18009285c`
- `0x1800929c4`
- `0x180092b08`
- `0x180092c08`
- `0x180092c8c`
- `0x180092d40`
- `0x180092e28`
- `0x180092eec`
- `0x180092f5c`
- `0x180093010`
- `0x180093098`
- `0x180093114`
- `0x1800931c4`
- `0x180093264`
- `0x1800932fc`
- `0x1800933d8`
- `0x180093444`
- `0x1800934e0`
- `0x180093568`
- `0x180093668`
- `0x1800936f0`
- `0x18009376c`
- `0x1800937d8`
- `0x180093848`
- `0x1800938c0`
- `0x180093944`
- `0x1800939b0`
- `0x180093a30`
- `0x180093ab4`
- `0x180093b50`
- `0x180093be0`

## callees

- `0x18006b58c`
- `0x18006f288`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18006b6dd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18006b6dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b700`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b700`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b66f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b66f`

## pseudocode

```c
ULONG FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  ULONG result; // eax
  void *v4; // rbx
  LPVOID v5; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v9[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  result = FastWppInitState;
  EventDescriptor = 0;
  UserData = 0;
  *(_OWORD *)dwBytes = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor.Id = a2;
    EventDescriptor.Level = HIBYTE(a1);
    v4 = 0;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE4(dwBytes[1]) = 0;
    LODWORD(dwBytes[1]) = 256;
    EventDescriptor.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    dwBytes[0] = (SIZE_T)v9;
    FastWppPackEvent((__int64 *)va, v9, 256, &dwBytes[1]);
    if ( LODWORD(dwBytes[1]) > 0x100 )
    {
      v5 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, LODWORD(dwBytes[1]));
      v4 = v5;
      if ( v5 )
      {
        dwBytes[0] = (SIZE_T)v5;
        FastWppPackEvent((__int64 *)va, v5, LODWORD(dwBytes[1]), &dwBytes[1]);
      }
      else
      {
        LODWORD(dwBytes[1]) = 256;
      }
    }
    result = EventWriteEx(FastWppRegHandle, &EventDescriptor, 0, 0, 0, 0, 2u, &UserData);
    if ( v4 )
      return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18006b58c  mov     [rsp-8+arg_10], r8
0x18006b591  mov     [rsp-8+arg_18], r9
0x18006b596  push    rbp
0x18006b597  push    rbx
0x18006b598  push    r14
0x18006b59a  lea     rbp, [rsp-90h]
0x18006b5a2  sub     rsp, 190h
0x18006b5a9  mov     rax, cs:__security_cookie
0x18006b5b0  xor     rax, rsp
0x18006b5b3  mov     [rbp+0A0h+var_20], rax
0x18006b5ba  mov     eax, cs:FastWppInitState
0x18006b5c0  xorps   xmm1, xmm1
0x18006b5c3  mov     [rsp+1A0h+var_160], 0
0x18006b5cc  xorps   xmm0, xmm0
0x18006b5cf  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x18006b5d4  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x18006b5d9  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x18006b5de  cmp     eax, 2
0x18006b5e1  jnz     loc_18006B70C
0x18006b5e7  movzx   eax, cx
0x18006b5ea  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x18006b5ef  shr     ax, 8
0x18006b5f3  lea     r14, [rbp+0A0h+arg_18]
0x18006b5fa  mov     [rsp+1A0h+EventDescriptor.Level], al
0x18006b5fe  lea     r9, [rsp+1A0h+dwBytes+8]
0x18006b603  xor     ebx, ebx
0x18006b605  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x18006b60a  mov     r8d, 100h
0x18006b610  mov     [rsp+1A0h+var_148.Size], 10h
0x18006b618  lea     rdx, [rbp+0A0h+var_120]
0x18006b61c  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x18006b620  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18006b628  lea     eax, [rbx+1]
0x18006b62b  shl     rax, cl
0x18006b62e  mov     rcx, r14
0x18006b631  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x18006b636  mov     rax, [rbp+0A0h+arg_10]
0x18006b63d  mov     [rsp+1A0h+var_148.Ptr], rax
0x18006b642  lea     rax, [rbp+0A0h+var_120]
0x18006b646  mov     [rsp+1A0h+dwBytes], rax
0x18006b64b  call    FastWppPackEvent
0x18006b650  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18006b658  jbe     short loc_18006B6A7
0x18006b65a  mov     rcx, gs:60h
0x18006b663  lea     edx, [rbx+8]; dwFlags
0x18006b666  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x18006b66b  mov     rcx, [rcx+30h]; hHeap
0x18006b66f  call    cs:__imp_HeapAlloc
0x18006b676  nop     dword ptr [rax+rax+00h]
0x18006b67b  mov     rbx, rax
0x18006b67e  test    rax, rax
0x18006b681  jz      short loc_18006B69F
0x18006b683  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x18006b688  lea     r9, [rsp+1A0h+dwBytes+8]
0x18006b68d  mov     rdx, rax
0x18006b690  mov     [rsp+1A0h+dwBytes], rax
0x18006b695  mov     rcx, r14
0x18006b698  call    FastWppPackEvent
0x18006b69d  jmp     short loc_18006B6A7
0x18006b69f  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18006b6a7  mov     rcx, cs:FastWppRegHandle; RegHandle
0x18006b6ae  lea     rax, [rsp+1A0h+var_148]
0x18006b6b3  mov     [rsp+1A0h+UserData], rax; UserData
0x18006b6b8  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x18006b6bd  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x18006b6c5  xor     r9d, r9d; Flags
0x18006b6c8  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x18006b6d1  xor     r8d, r8d; Filter
0x18006b6d4  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x18006b6dd  call    cs:__imp_EventWriteEx
0x18006b6e4  nop     dword ptr [rax+rax+00h]
0x18006b6e9  test    rbx, rbx
0x18006b6ec  jz      short loc_18006B70C
0x18006b6ee  mov     rcx, gs:60h
0x18006b6f7  mov     r8, rbx; lpMem
0x18006b6fa  xor     edx, edx; dwFlags
0x18006b6fc  mov     rcx, [rcx+30h]; hHeap
0x18006b700  call    cs:__imp_HeapFree
0x18006b707  nop     dword ptr [rax+rax+00h]
0x18006b70c  mov     rcx, [rbp+0A0h+var_20]
0x18006b713  xor     rcx, rsp; StackCookie
0x18006b716  call    __security_check_cookie
0x18006b71b  add     rsp, 190h
0x18006b722  pop     r14
0x18006b724  pop     rbx
0x18006b725  pop     rbp
0x18006b726  retn
```
