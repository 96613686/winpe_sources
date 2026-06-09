# Sens::Activity::Activity(SENS_EVENT_TYPE)

- ea: `0x180005650`
- end: `0x18000582a`
- name: `??0Activity@Sens@@QEAA@W4SENS_EVENT_TYPE@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e70`
- `0x180004f10`
- `0x1800050b0`
- `0x1800051d0`

## callees

- `0x180005650`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800057fc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800057fc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800056c3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800056c3`

## pseudocode

```c
__int64 __fastcall Sens::Activity::Activity(__int64 a1, int a2)
{
  const GUID *v3; // rdi
  bool v4; // zf
  const GUID *v5; // r9
  _DWORD v7[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v8; // [rsp+38h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  char *v11; // [rsp+60h] [rbp-48h]
  int v12; // [rsp+68h] [rbp-40h]
  int v13; // [rsp+6Ch] [rbp-3Ch]
  __int64 *v14; // [rsp+70h] [rbp-38h]
  __int64 v15; // [rsp+78h] [rbp-30h]
  _DWORD *v16; // [rsp+80h] [rbp-28h]
  __int64 v17; // [rsp+88h] [rbp-20h]

  *(_DWORD *)a1 = 0;
  *(_BYTE *)(a1 + 4) = 0;
  *(_DWORD *)(a1 + 40) = a2;
  if ( (unsigned int)dword_180011008 > 5
    && (qword_180011018 & 0x400000000000LL) != 0
    && (qword_180011020 & 0x400000000000LL) == qword_180011020 )
  {
    v3 = (const GUID *)(a1 + 8);
    EventActivityIdControl(3u, (LPGUID)(a1 + 8));
  }
  else
  {
    v3 = (const GUID *)(a1 + 8);
    *(_OWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)a1 = 1;
  if ( (unsigned int)dword_180011008 > 5
    && (qword_180011018 & 0x400000000000LL) != 0
    && (qword_180011020 & 0x400000000000LL) == qword_180011020 )
  {
    v4 = *(_BYTE *)(a1 + 4) == 0;
    v7[0] = *(_DWORD *)(a1 + 40);
    v8 = 0x1000000;
    if ( v4
      || (v5 = (const GUID *)(a1 + 24), !*(_DWORD *)(a1 + 24))
      && !*(_DWORD *)(a1 + 28)
      && !*(_DWORD *)(a1 + 32)
      && !*(_DWORD *)(a1 + 36) )
    {
      v5 = 0;
    }
    v17 = 4;
    v16 = v7;
    v15 = 8;
    v14 = &v8;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180011010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Size = *(unsigned __int16 *)off_180011010;
    v11 = &byte_18000E307;
    UserData.Reserved = 2;
    v12 = 52;
    v13 = 1;
    v7[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, v3, v5, 4u, &UserData);
  }
  return a1;
}

```

## disassembly

```asm
0x180005650  mov     [rsp+arg_8], rbx
0x180005655  mov     [rsp+arg_10], rsi
0x18000565a  push    rdi
0x18000565b  sub     rsp, 0A0h
0x180005662  mov     rax, cs:__security_cookie
0x180005669  xor     rax, rsp
0x18000566c  mov     [rsp+0A8h+var_18], rax
0x180005674  mov     dword ptr [rcx], 0
0x18000567a  mov     rbx, rcx
0x18000567d  mov     byte ptr [rcx+4], 0
0x180005681  mov     rsi, 400000000000h
0x18000568b  mov     [rcx+28h], edx
0x18000568e  mov     eax, cs:dword_180011008
0x180005694  cmp     eax, 5
0x180005697  jbe     short loc_1800056CB
0x180005699  mov     rcx, cs:qword_180011020
0x1800056a0  mov     rax, cs:qword_180011018
0x1800056a7  test    rsi, rax
0x1800056aa  jz      short loc_1800056CB
0x1800056ac  mov     rax, rcx
0x1800056af  and     rax, rsi
0x1800056b2  cmp     rax, rcx
0x1800056b5  jnz     short loc_1800056CB
0x1800056b7  lea     rdi, [rbx+8]
0x1800056bb  mov     ecx, 3; ControlCode
0x1800056c0  mov     rdx, rdi; ActivityId
0x1800056c3  call    cs:__imp_EventActivityIdControl
0x1800056c9  jmp     short loc_1800056D5
0x1800056cb  lea     rdi, [rbx+8]
0x1800056cf  xorps   xmm0, xmm0
0x1800056d2  movups  xmmword ptr [rdi], xmm0
0x1800056d5  mov     dword ptr [rbx], 1
0x1800056db  mov     eax, cs:dword_180011008
0x1800056e1  cmp     eax, 5
0x1800056e4  jbe     loc_180005802
0x1800056ea  mov     rcx, cs:qword_180011020
0x1800056f1  mov     rax, cs:qword_180011018
0x1800056f8  test    rsi, rax
0x1800056fb  jz      loc_180005802
0x180005701  mov     rax, rcx
0x180005704  and     rax, rsi
0x180005707  cmp     rax, rcx
0x18000570a  jnz     loc_180005802
0x180005710  cmp     byte ptr [rbx+4], 0
0x180005714  mov     eax, [rbx+28h]
0x180005717  mov     [rsp+0A8h+var_78], eax
0x18000571b  mov     [rsp+0A8h+var_70], 1000000h
0x180005724  jz      short loc_180005745
0x180005726  cmp     dword ptr [rbx+18h], 0
0x18000572a  lea     r9, [rbx+18h]
0x18000572e  jnz     short loc_180005748
0x180005730  cmp     dword ptr [r9+4], 0
0x180005735  jnz     short loc_180005748
0x180005737  cmp     dword ptr [r9+8], 0
0x18000573c  jnz     short loc_180005748
0x18000573e  cmp     dword ptr [r9+0Ch], 0
0x180005743  jnz     short loc_180005748
0x180005745  xor     r9d, r9d; RelatedActivityId
0x180005748  mov     [rsp+0A8h+var_20], 4
0x180005754  lea     rax, [rsp+0A8h+var_78]
0x180005759  mov     [rsp+0A8h+var_28], rax
0x180005761  lea     rcx, _TraceLoggingMetadataEnd
0x180005768  lea     rax, [rsp+0A8h+var_70]
0x18000576d  mov     [rsp+0A8h+var_30], 8
0x180005776  mov     [rsp+0A8h+var_38], rax
0x18000577b  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x180005780  movzx   eax, cs:word_18000E2FD
0x180005787  mov     r8, rdi; ActivityId
0x18000578a  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x18000578e  mov     rax, cs:off_180011010
0x180005795  mov     [rsp+0A8h+var_58.Ptr], rax
0x18000579a  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x1800057a2  mov     [rsp+0A8h+EventDescriptor.Keyword], rsi
0x1800057a7  movzx   eax, word ptr [rax]
0x1800057aa  mov     [rsp+0A8h+var_58.Size], eax
0x1800057ae  lea     rax, byte_18000E307
0x1800057b5  mov     [rsp+0A8h+var_48], rax
0x1800057ba  lea     rax, _TraceLoggingMetadata
0x1800057c1  sub     ecx, eax
0x1800057c3  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x1800057cb  mov     [rsp+0A8h+var_40], 34h ; '4'
0x1800057d3  lea     rax, [rsp+0A8h+var_58]
0x1800057d8  mov     [rsp+0A8h+var_3C], 1
0x1800057e0  mov     [rsp+0A8h+var_74], ecx
0x1800057e4  mov     ecx, [rsp+0A8h+var_74]
0x1800057e8  mov     rcx, cs:RegHandle; RegHandle
0x1800057ef  mov     [rsp+0A8h+UserData], rax; UserData
0x1800057f4  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x1800057fc  call    cs:__imp_EventWriteTransfer
0x180005802  mov     rax, rbx
0x180005805  mov     rcx, [rsp+0A8h+var_18]
0x18000580d  xor     rcx, rsp; StackCookie
0x180005810  call    __security_check_cookie
0x180005815  lea     r11, [rsp+0A8h+var_8]
0x18000581d  mov     rbx, [r11+18h]
0x180005821  mov     rsi, [r11+20h]
0x180005825  mov     rsp, r11
0x180005828  pop     rdi
0x180005829  retn
```
