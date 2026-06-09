# WapCreateProtocolHandle

- ea: `0x1800829c0`
- end: `0x180082c3c`
- name: `WapCreateProtocolHandle`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082f50`

## callees

- `0x180013284`
- `0x180013820`
- `0x18001d2f0`
- `0x18001eb50`
- `0x180039e50`
- `0x18003a4a0`
- `0x18004e4f0`
- `0x18005e948`
- `0x180065720`
- `0x1800722f0`
- `0x18007630c`
- `0x1800825e4`
- `0x18008269c`
- `0x1800829c0`
- `0x180082c44`
- `0x180098010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082afd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082c06`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082afd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082c06`

## pseudocode

```c
__int64 __fastcall WapCreateProtocolHandle(int a1, __int64 *a2)
{
  char v3; // r13
  unsigned int v4; // eax
  int v5; // ecx
  __int64 v6; // rsi
  unsigned int Handle; // edi
  __int64 v8; // r12
  unsigned int ProtocolObject; // eax
  GUID *v10; // rbx
  __int64 v11; // r8
  volatile signed __int32 *v12; // rbx
  int v14; // [rsp+20h] [rbp-79h]
  __int64 v15; // [rsp+50h] [rbp-49h] BYREF
  __int64 v16; // [rsp+58h] [rbp-41h] BYREF
  GUID *v17; // [rsp+60h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-31h] BYREF
  __int64 v19; // [rsp+70h] [rbp-29h] BYREF
  __int64 v20; // [rsp+78h] [rbp-21h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-19h] BYREF
  __int128 v22; // [rsp+88h] [rbp-11h]
  GUID ActivityId; // [rsp+98h] [rbp-1h] BYREF
  int v24; // [rsp+A8h] [rbp+Fh]

  hObject = (HANDLE)-1LL;
  *a2 = 0;
  v24 = 0;
  v17 = 0;
  v15 = 0;
  lpMem = 0;
  v19 = 0;
  v3 = a1;
  v20 = 0;
  v16 = 0;
  v22 = 0;
  ActivityId = 0;
  v4 = WaFinishHttpRequestUpgrade(
         a1,
         (unsigned int)&v15,
         (unsigned int)&lpMem,
         (unsigned int)&v19,
         (__int64)&v20,
         (__int64)&v16);
  v6 = v15;
  Handle = v4;
  if ( !v4 )
  {
    WaEtwBeginActivityId((LPGUID)(v15 + 120));
    v8 = *(_QWORD *)(v6 + 24);
    Handle = WaImpersonateSessionToken(v6, (__int64 *)&hObject);
    if ( !Handle )
    {
      ProtocolObject = WapCreateProtocolObject(
                         v19,
                         (unsigned int)&v20,
                         v16,
                         (unsigned int)&lpMem,
                         (__int64)&v15,
                         (__int64)&v17);
      v6 = v15;
      Handle = ProtocolObject;
      v10 = v17;
      if ( !ProtocolObject )
      {
        Handle = WaAllocateHandle((struct _SLIST_ENTRY *)v17, 9, a2);
        if ( Handle )
        {
          *a2 = 0;
        }
        else
        {
          *(_QWORD *)v10[4].Data4 = *a2;
          WaEtwGenerateActivityIdFromHandle(*a2, (int)v10, v11, (__int64)&v10[20]);
          if ( (_BYTE)v24 )
            EventActivityIdControl(2u, &ActivityId);
          WaEtwBeginActivityId(v10 + 20);
          if ( (Microsoft_Windows_WebIOEnableBits & 4) != 0 )
            McTemplateU0pxpxpxq_EventWriteTransfer(
              v5,
              (unsigned int)ApiCreateProtocolHandle,
              (_DWORD)v10,
              *a2,
              v14,
              v3,
              v6,
              v8,
              0);
          v10 = 0;
        }
      }
      if ( v10 )
      {
        WaProtocolConnectionAbort(v10, Handle);
        WaDereferenceProtocolObject(v10);
      }
    }
  }
  v12 = (volatile signed __int32 *)lpMem;
  if ( lpMem )
  {
    (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(v19 + 56))(lpMem, 0, Handle);
    if ( _InterlockedExchangeAdd(v12 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v12);
  }
  if ( v6 )
    WaDereferenceSession(v6);
  if ( v20 )
  {
    v16 = v20;
    WxFreeHeapEx(&v16);
  }
  if ( Handle && (Microsoft_Windows_WebIOEnableBits & 4) != 0 )
    McTemplateU0pxpxpxq_EventWriteTransfer(v5, (unsigned int)ApiCreateProtocolHandleFailed, 0, 0, v14, 0, 0, 0, Handle);
  WaRestoreToken(hObject);
  if ( (_BYTE)v24 )
    EventActivityIdControl(2u, &ActivityId);
  return Handle;
}

```

## disassembly

```asm
0x1800829c0  mov     [rsp-8+arg_10], rbx
0x1800829c5  push    rbp
0x1800829c6  push    rsi
0x1800829c7  push    rdi
0x1800829c8  push    r12
0x1800829ca  push    r13
0x1800829cc  push    r14
0x1800829ce  push    r15
0x1800829d0  lea     rbp, [rsp-27h]
0x1800829d5  sub     rsp, 0C0h
0x1800829dc  mov     rax, cs:__security_cookie
0x1800829e3  xor     rax, rsp
0x1800829e6  mov     [rbp+57h+var_40], rax
0x1800829ea  xor     r15d, r15d
0x1800829ed  mov     [rbp+57h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800829f5  xor     eax, eax
0x1800829f7  mov     [rdx], r15
0x1800829fa  mov     [rbp+57h+var_48], eax
0x1800829fd  lea     r9, [rbp+57h+var_80]
0x180082a01  xorps   xmm0, xmm0
0x180082a04  mov     [rbp+57h+var_90], r15
0x180082a08  lea     rax, [rbp+57h+var_98]
0x180082a0c  mov     [rbp+57h+var_A0], r15
0x180082a10  mov     [rsp+0F0h+var_C8], rax
0x180082a15  lea     r8, [rbp+57h+lpMem]
0x180082a19  lea     rax, [rbp+57h+var_78]
0x180082a1d  mov     [rbp+57h+lpMem], r15
0x180082a21  mov     r14, rdx
0x180082a24  mov     [rsp+0F0h+var_D0], rax
0x180082a29  lea     rdx, [rbp+57h+var_A0]
0x180082a2d  mov     [rbp+57h+var_80], r15
0x180082a31  mov     r13, rcx
0x180082a34  mov     [rbp+57h+var_78], r15
0x180082a38  mov     [rbp+57h+var_98], r15
0x180082a3c  movups  [rbp+57h+var_68], xmm0
0x180082a40  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180082a44  call    WaFinishHttpRequestUpgrade
0x180082a49  mov     rsi, [rbp+57h+var_A0]
0x180082a4d  mov     edi, eax
0x180082a4f  test    eax, eax
0x180082a51  jnz     loc_180082B66
0x180082a57  lea     rcx, [rsi+78h]; ActivityId
0x180082a5b  xor     edx, edx
0x180082a5d  lea     r8, [rbp+57h+var_68]
0x180082a61  call    WaEtwBeginActivityId
0x180082a66  mov     r12, [rsi+18h]
0x180082a6a  lea     rdx, [rbp+57h+hObject]
0x180082a6e  mov     rcx, rsi
0x180082a71  call    WaImpersonateSessionToken
0x180082a76  mov     edi, eax
0x180082a78  test    eax, eax
0x180082a7a  jnz     loc_180082B66
0x180082a80  mov     r8, [rbp+57h+var_98]
0x180082a84  lea     rax, [rbp+57h+var_90]
0x180082a88  mov     rcx, [rbp+57h+var_80]
0x180082a8c  lea     r9, [rbp+57h+lpMem]
0x180082a90  mov     [rsp+0F0h+var_C8], rax
0x180082a95  lea     rdx, [rbp+57h+var_78]
0x180082a99  lea     rax, [rbp+57h+var_A0]
0x180082a9d  mov     [rsp+0F0h+var_D0], rax
0x180082aa2  call    WapCreateProtocolObject
0x180082aa7  mov     rsi, [rbp+57h+var_A0]
0x180082aab  mov     edi, eax
0x180082aad  mov     rbx, [rbp+57h+var_90]
0x180082ab1  test    eax, eax
0x180082ab3  jnz     loc_180082B4F
0x180082ab9  mov     r8, r14
0x180082abc  lea     edx, [rax+9]
0x180082abf  mov     rcx, rbx
0x180082ac2  call    WaAllocateHandle
0x180082ac7  mov     edi, eax
0x180082ac9  test    eax, eax
0x180082acb  jz      short loc_180082AD2
0x180082acd  mov     [r14], r15
0x180082ad0  jmp     short loc_180082B4F
0x180082ad2  mov     rax, [r14]
0x180082ad5  lea     r15, [rbx+140h]
0x180082adc  mov     [rbx+48h], rax
0x180082ae0  mov     r9, r15
0x180082ae3  mov     rcx, [r14]
0x180082ae6  mov     rdx, rbx
0x180082ae9  call    WaEtwGenerateActivityIdFromHandle
0x180082aee  cmp     byte ptr [rbp+57h+var_48], 0
0x180082af2  jz      short loc_180082B09
0x180082af4  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180082af8  mov     ecx, 2; ControlCode
0x180082afd  call    cs:__imp_EventActivityIdControl
0x180082b04  nop     dword ptr [rax+rax+00h]
0x180082b09  lea     r8, [rbp+57h+var_68]
0x180082b0d  mov     edx, 0Ch
0x180082b12  mov     rcx, r15; ActivityId
0x180082b15  call    WaEtwBeginActivityId
0x180082b1a  xor     r15d, r15d
0x180082b1d  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 4
0x180082b24  jz      short loc_180082B4C
0x180082b26  mov     r9, [r14]
0x180082b29  lea     rdx, ApiCreateProtocolHandle
0x180082b30  mov     [rsp+0F0h+var_B0], r15d
0x180082b35  mov     r8, rbx
0x180082b38  mov     [rsp+0F0h+var_B8], r12
0x180082b3d  mov     [rsp+0F0h+var_C0], rsi
0x180082b42  mov     [rsp+0F0h+var_C8], r13
0x180082b47  call    McTemplateU0pxpxpxq_EventWriteTransfer
0x180082b4c  mov     rbx, r15
0x180082b4f  test    rbx, rbx
0x180082b52  jz      short loc_180082B66
0x180082b54  mov     edx, edi
0x180082b56  mov     rcx, rbx
0x180082b59  call    WaProtocolConnectionAbort
0x180082b5e  mov     rcx, rbx
0x180082b61  call    WaDereferenceProtocolObject
0x180082b66  mov     rbx, [rbp+57h+lpMem]
0x180082b6a  test    rbx, rbx
0x180082b6d  jz      short loc_180082B99
0x180082b6f  mov     rax, [rbp+57h+var_80]
0x180082b73  mov     r8d, edi
0x180082b76  xor     edx, edx
0x180082b78  mov     rcx, rbx
0x180082b7b  mov     rax, [rax+38h]
0x180082b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b84  or      eax, 0FFFFFFFFh
0x180082b87  lock xadd [rbx+4], eax
0x180082b8c  cmp     eax, 1
0x180082b8f  jnz     short loc_180082B99
0x180082b91  mov     rcx, rbx; lpMem
0x180082b94  call    WaDestroyConnection
0x180082b99  test    rsi, rsi
0x180082b9c  jz      short loc_180082BA6
0x180082b9e  mov     rcx, rsi
0x180082ba1  call    WaDereferenceSession
0x180082ba6  mov     rax, [rbp+57h+var_78]
0x180082baa  test    rax, rax
0x180082bad  jz      short loc_180082BBC
0x180082baf  lea     rcx, [rbp+57h+var_98]
0x180082bb3  mov     [rbp+57h+var_98], rax
0x180082bb7  call    WxFreeHeapEx
0x180082bbc  test    edi, edi
0x180082bbe  jz      short loc_180082BEE
0x180082bc0  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 4
0x180082bc7  jz      short loc_180082BEE
0x180082bc9  mov     [rsp+0F0h+var_B0], edi
0x180082bcd  lea     rdx, ApiCreateProtocolHandleFailed
0x180082bd4  mov     [rsp+0F0h+var_B8], r15
0x180082bd9  xor     r9d, r9d
0x180082bdc  mov     [rsp+0F0h+var_C0], r15
0x180082be1  xor     r8d, r8d
0x180082be4  mov     [rsp+0F0h+var_C8], r15
0x180082be9  call    McTemplateU0pxpxpxq_EventWriteTransfer
0x180082bee  mov     rcx, [rbp+57h+hObject]; hObject
0x180082bf2  call    WaRestoreToken
0x180082bf7  cmp     byte ptr [rbp+57h+var_48], r15b
0x180082bfb  jz      short loc_180082C12
0x180082bfd  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180082c01  mov     ecx, 2; ControlCode
0x180082c06  call    cs:__imp_EventActivityIdControl
0x180082c0d  nop     dword ptr [rax+rax+00h]
0x180082c12  mov     eax, edi
0x180082c14  mov     rcx, [rbp+57h+var_40]
0x180082c18  xor     rcx, rsp; StackCookie
0x180082c1b  call    __security_check_cookie
0x180082c20  mov     rbx, [rsp+0F0h+arg_10]
0x180082c28  add     rsp, 0C0h
0x180082c2f  pop     r15
0x180082c31  pop     r14
0x180082c33  pop     r13
0x180082c35  pop     r12
0x180082c37  pop     rdi
0x180082c38  pop     rsi
0x180082c39  pop     rbp
0x180082c3a  retn
```
