# VsmmEpfpWorker

- ea: `0x140030030`
- end: `0x140030287`
- name: `VsmmEpfpWorker`
- size: `599`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140021606`
- `0x140021650`
- `0x140021d40`
- `0x140030030`
- `0x140030290`
- `0x1400303c0`
- `0x140030790`
- `0x1400307d0`
- `0x140030800`
- `0x1400f0934`
- `0x1400f1598`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140030144`
- `ntoskrnl!EtwEventEnabled` at `0x140030144`
- `ntoskrnl!EtwActivityIdControl` at `0x140030182`
- `ntoskrnl!EtwActivityIdControl` at `0x140030182`
- `ntoskrnl!EtwWrite` at `0x140030200`
- `ntoskrnl!EtwWrite` at `0x140030200`

## pseudocode

```c
__int64 __fastcall VsmmEpfpWorker(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  char v4; // cl
  unsigned int v5; // r13d
  __int64 v6; // rdi
  _BYTE *v7; // r15
  int v8; // eax
  __int64 v9; // r14
  __int64 v10; // r9
  int v11; // r9d
  int v12; // eax
  __int64 v13; // rdx
  int v14; // ebx
  __int64 v15; // r14
  __int64 v16; // rsi
  GUID v17; // xmm1
  char v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-B0h] BYREF
  GUID v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  __int64 *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  _BYTE v29[4096]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = *(unsigned int *)(a2 + 84);
  v4 = *(_BYTE *)(a2 + 96);
  v5 = *(_DWORD *)(a2 + 80);
  v6 = *(_QWORD *)(a2 + 48);
  v7 = *(_BYTE **)(a2 + 88);
  *(_QWORD *)&ActivityId.Data1 = *(_QWORD *)(a2 + 64);
  v8 = *(_DWORD *)(a2 + 72);
  v21[0] = 0;
  LODWORD(v20) = v8;
  v23.Data1 = v5;
  *(_DWORD *)&v23.Data2 = v3;
  v19 = v4;
  if ( v8 )
  {
    v9 = 0;
    memmove(v29, v7, 8 * v3);
    v7 = v29;
  }
  else
  {
    v9 = *(_QWORD *)&v23.Data1;
  }
  VidLockAcquireExclusive(v6 + 10480);
  v10 = *(_QWORD *)(v6 + 10760);
  *(_QWORD *)a2 = *(_QWORD *)(v10 + 40);
  *(_QWORD *)(v10 + 40) = a2;
  VidLockRelease(v6 + 10480);
  if ( (_DWORD)v20 )
  {
    v12 = VsmmHintApplyRange(v6, v5, (__int64)v7, v3, 0, v21);
  }
  else
  {
    LOBYTE(v11) = v19;
    v12 = VsmmHandleVaBackedMemoryIntercept(v6, v23.Data1, (_DWORD)v7, v11, 0);
  }
  v14 = v12;
  if ( v9 )
    VidRefCounterDec(v9 + 8, 0);
  if ( v14 < 0 )
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v6 + 10760) + 48LL), 4u);
  v15 = *(_QWORD *)&ActivityId.Data1;
  VsmmEpfpCompletionDeliver(v6, v13, *(_QWORD *)&ActivityId.Data1);
  if ( VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_EPF_FAULT_STOP) )
  {
    v16 = *(_QWORD *)(v6 + 648);
    v17 = 0;
    v23 = 0;
    ActivityId = 0;
    if ( VID_TRACE_ETW_GUID_Context )
    {
      EtwActivityIdControl(1u, &ActivityId);
      v17 = ActivityId;
    }
    v20 = v14;
    v23 = v17;
    UserData.Ptr = (ULONGLONG)&ActivityId;
    v25 = v21;
    v27 = &v20;
    *(_QWORD *)v21 = v15;
    *(_QWORD *)&ActivityId.Data1 = v16;
    *(_QWORD *)&UserData.Size = 8;
    v26 = 8;
    v28 = 8;
    EtwWrite(VID_TRACE_ETW_GUID_Context, &VID_EPF_FAULT_STOP, &v23, 3u, &UserData);
  }
  return VidOpCtrlFinish(v6 + 10488);
}

```

## disassembly

```asm
0x140030030  push    rbp
0x140030032  push    rbx
0x140030033  push    rsi
0x140030034  push    rdi
0x140030035  push    r12
0x140030037  push    r13
0x140030039  push    r14
0x14003003b  push    r15
0x14003003d  lea     rbp, [rsp-0FC8h]
0x140030045  mov     eax, 10C8h
0x14003004a  call    __chkstk_0
0x14003004f  sub     rsp, rax
0x140030052  mov     rax, cs:__security_cookie
0x140030059  xor     rax, rsp
0x14003005c  mov     [rbp+1000h+var_50], rax
0x140030063  mov     rax, [rdx+40h]
0x140030067  mov     rsi, rdx
0x14003006a  mov     r12d, [rdx+54h]
0x14003006e  mov     cl, [rdx+60h]
0x140030071  mov     r13d, [rdx+50h]
0x140030075  mov     rdi, [rdx+30h]
0x140030079  mov     r15, [rdx+58h]
0x14003007d  mov     qword ptr [rsp+1100h+ActivityId.Data1], rax
0x140030082  mov     eax, [rdx+48h]
0x140030085  mov     [rsp+1100h+var_10C0], 0
0x14003008d  mov     dword ptr [rsp+1100h+var_10C8], eax
0x140030091  mov     [rsp+1100h+var_10A0.Data1], r13d
0x140030096  mov     dword ptr [rsp+1100h+var_10A0.Data2], r12d
0x14003009b  mov     [rsp+1100h+var_10D0], cl
0x14003009f  test    eax, eax
0x1400300a1  jnz     loc_14003023C
0x1400300a7  mov     r14, qword ptr [rsp+1100h+var_10A0.Data1]
0x1400300ac  lea     rbx, [rdi+28F0h]
0x1400300b3  mov     rcx, rbx
0x1400300b6  call    VidLockAcquireExclusive
0x1400300bb  mov     r9, [rdi+2A08h]
0x1400300c2  mov     rcx, rbx
0x1400300c5  mov     rax, [r9+28h]
0x1400300c9  mov     [rsi], rax
0x1400300cc  mov     [r9+28h], rsi
0x1400300d0  call    VidLockRelease
0x1400300d5  xor     ecx, ecx
0x1400300d7  mov     r8, r15
0x1400300da  cmp     dword ptr [rsp+1100h+var_10C8], ecx
0x1400300de  jz      loc_14003025B
0x1400300e4  lea     rax, [rsp+1100h+var_10C0]
0x1400300e9  mov     r9d, r12d
0x1400300ec  mov     [rsp+1100h+var_10D8], rax
0x1400300f1  mov     edx, r13d
0x1400300f4  mov     byte ptr [rsp+1100h+UserData], cl
0x1400300f8  mov     rcx, rdi
0x1400300fb  call    VsmmHintApplyRange
0x140030100  xor     r15d, r15d
0x140030103  mov     ebx, eax
0x140030105  test    r14, r14
0x140030108  jz      short loc_140030115
0x14003010a  lea     rcx, [r14+8]
0x14003010e  xor     edx, edx
0x140030110  call    VidRefCounterDec
0x140030115  test    ebx, ebx
0x140030117  js      loc_140030276
0x14003011d  mov     r14, qword ptr [rsp+1100h+ActivityId.Data1]
0x140030122  mov     rcx, rdi
0x140030125  mov     r8, r14
0x140030128  call    VsmmEpfpCompletionDeliver
0x14003012d  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x140030134  test    rcx, rcx
0x140030137  jz      loc_14003020C
0x14003013d  lea     rdx, VID_EPF_FAULT_STOP; EventDescriptor
0x140030144  call    cs:__imp_EtwEventEnabled
0x14003014b  nop     dword ptr [rax+rax+00h]
0x140030150  test    al, al
0x140030152  jz      loc_14003020C
0x140030158  cmp     cs:VID_TRACE_ETW_GUID_Context, r15
0x14003015f  xorps   xmm0, xmm0
0x140030162  mov     rsi, [rdi+288h]
0x140030169  xorps   xmm1, xmm1
0x14003016c  movups  xmmword ptr [rsp+1100h+var_10A0.Data1], xmm0
0x140030171  movaps  xmmword ptr [rsp+1100h+ActivityId.Data1], xmm1
0x140030176  jz      short loc_140030193
0x140030178  lea     rdx, [rsp+1100h+ActivityId]; ActivityId
0x14003017d  mov     ecx, 1; ControlCode
0x140030182  call    cs:__imp_EtwActivityIdControl
0x140030189  nop     dword ptr [rax+rax+00h]
0x14003018e  movaps  xmm1, xmmword ptr [rsp+1100h+ActivityId.Data1]
0x140030193  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x14003019a  lea     r8, [rsp+1100h+var_10A0]; ActivityId
0x14003019f  movsxd  rax, ebx
0x1400301a2  lea     rdx, VID_EPF_FAULT_STOP; EventDescriptor
0x1400301a9  mov     [rsp+1100h+var_10C8], rax
0x1400301ae  mov     r9d, 3; UserDataCount
0x1400301b4  lea     rax, [rsp+1100h+ActivityId]
0x1400301b9  movdqa  xmmword ptr [rsp+1100h+var_10A0.Data1], xmm1
0x1400301bf  mov     [rbp+1000h+var_1080.Ptr], rax
0x1400301c3  lea     rax, [rsp+1100h+var_10C0]
0x1400301c8  mov     [rbp+1000h+var_1070], rax
0x1400301cc  lea     rax, [rsp+1100h+var_10C8]
0x1400301d1  mov     [rbp+1000h+var_1060], rax
0x1400301d5  lea     rax, [rbp+1000h+var_1080]
0x1400301d9  mov     [rsp+1100h+UserData], rax; UserData
0x1400301de  mov     qword ptr [rsp+1100h+var_10C0], r14
0x1400301e3  mov     qword ptr [rsp+1100h+ActivityId.Data1], rsi
0x1400301e8  mov     qword ptr [rbp+1000h+var_1080.Size], 8
0x1400301f0  mov     [rbp+1000h+var_1068], 8
0x1400301f8  mov     [rbp+1000h+var_1058], 8
0x140030200  call    cs:__imp_EtwWrite
0x140030207  nop     dword ptr [rax+rax+00h]
0x14003020c  lea     rcx, [rdi+28F8h]
0x140030213  call    VidOpCtrlFinish
0x140030218  mov     rcx, [rbp+1000h+var_50]
0x14003021f  xor     rcx, rsp; StackCookie
0x140030222  call    __security_check_cookie
0x140030227  add     rsp, 10C8h
0x14003022e  pop     r15
0x140030230  pop     r14
0x140030232  pop     r13
0x140030234  pop     r12
0x140030236  pop     rdi
0x140030237  pop     rsi
0x140030238  pop     rbx
0x140030239  pop     rbp
0x14003023a  retn
0x14003023c  mov     r8, r12
0x14003023f  lea     rcx, [rbp+1000h+var_1050]; void *
0x140030243  shl     r8, 3; Size
0x140030247  xor     r14d, r14d
0x14003024a  mov     rdx, r15; Src
0x14003024d  call    memmove
0x140030252  lea     r15, [rbp+1000h+var_1050]
0x140030256  jmp     loc_1400300AC
0x14003025b  mov     r9b, [rsp+1100h+var_10D0]
0x140030260  mov     rdx, qword ptr [rsp+1100h+var_10A0.Data1]
0x140030265  mov     byte ptr [rsp+1100h+UserData], cl
0x140030269  mov     rcx, rdi
0x14003026c  call    VsmmHandleVaBackedMemoryIntercept
0x140030271  jmp     loc_140030100
0x140030276  mov     rax, [rdi+2A08h]
0x14003027d  lock add dword ptr [rax+30h], 4
0x140030282  jmp     loc_14003011D
```
