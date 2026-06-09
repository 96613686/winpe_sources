# VsmmEpfpWorker

- ea: `0x140030230`
- end: `0x140030487`
- name: `VsmmEpfpWorker`
- size: `599`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140021c16`
- `0x140021c60`
- `0x140022340`
- `0x140030230`
- `0x140030490`
- `0x1400305c0`
- `0x140030990`
- `0x1400309d0`
- `0x140030a00`
- `0x1400f30c4`
- `0x1400f409c`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140030382`
- `ntoskrnl!EtwActivityIdControl` at `0x140030382`
- `ntoskrnl!EtwEventEnabled` at `0x140030344`
- `ntoskrnl!EtwEventEnabled` at `0x140030344`
- `ntoskrnl!EtwWrite` at `0x140030400`
- `ntoskrnl!EtwWrite` at `0x140030400`

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
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rsi
  GUID v19; // xmm1
  char v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-B0h] BYREF
  GUID v25; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  __int64 *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  _BYTE v31[4096]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = *(unsigned int *)(a2 + 84);
  v4 = *(_BYTE *)(a2 + 96);
  v5 = *(_DWORD *)(a2 + 80);
  v6 = *(_QWORD *)(a2 + 48);
  v7 = *(_BYTE **)(a2 + 88);
  *(_QWORD *)&ActivityId.Data1 = *(_QWORD *)(a2 + 64);
  v8 = *(_DWORD *)(a2 + 72);
  LODWORD(v23[0]) = 0;
  LODWORD(v22) = v8;
  v25.Data1 = v5;
  *(_DWORD *)&v25.Data2 = v3;
  v21 = v4;
  if ( v8 )
  {
    v9 = 0;
    memmove(v31, v7, 8 * v3);
    v7 = v31;
  }
  else
  {
    v9 = *(_QWORD *)&v25.Data1;
  }
  VidLockAcquireExclusive(v6 + 10480);
  v10 = *(_QWORD *)(v6 + 10760);
  *(_QWORD *)a2 = *(_QWORD *)(v10 + 40);
  *(_QWORD *)(v10 + 40) = a2;
  VidLockRelease(v6 + 10480);
  if ( (_DWORD)v22 )
  {
    v12 = VsmmHintApplyRange(v6, v5, (_DWORD)v7, v3, 0, (__int64)v23);
  }
  else
  {
    LOBYTE(v11) = v21;
    v12 = VsmmHandleVaBackedMemoryIntercept(v6, v25.Data1, (_DWORD)v7, v11, 0);
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
    v18 = *(_QWORD *)(v6 + 648);
    v19 = 0;
    v25 = 0;
    ActivityId = 0;
    if ( VID_TRACE_ETW_GUID_Context )
    {
      EtwActivityIdControl(1u, &ActivityId);
      v19 = ActivityId;
    }
    v22 = v14;
    v25 = v19;
    UserData.Ptr = (ULONGLONG)&ActivityId;
    v27 = v23;
    v29 = &v22;
    v23[0] = v15;
    *(_QWORD *)&ActivityId.Data1 = v18;
    *(_QWORD *)&UserData.Size = 8;
    v28 = 8;
    v30 = 8;
    EtwWrite(VID_TRACE_ETW_GUID_Context, &VID_EPF_FAULT_STOP, &v25, 3u, &UserData);
  }
  return VidOpCtrlFinish(v6 + 10488, v16, v17);
}

```

## disassembly

```asm
0x140030230  push    rbp
0x140030232  push    rbx
0x140030233  push    rsi
0x140030234  push    rdi
0x140030235  push    r12
0x140030237  push    r13
0x140030239  push    r14
0x14003023b  push    r15
0x14003023d  lea     rbp, [rsp-0FC8h]
0x140030245  mov     eax, 10C8h
0x14003024a  call    __chkstk_0
0x14003024f  sub     rsp, rax
0x140030252  mov     rax, cs:__security_cookie
0x140030259  xor     rax, rsp
0x14003025c  mov     [rbp+1000h+var_50], rax
0x140030263  mov     rax, [rdx+40h]
0x140030267  mov     rsi, rdx
0x14003026a  mov     r12d, [rdx+54h]
0x14003026e  mov     cl, [rdx+60h]
0x140030271  mov     r13d, [rdx+50h]
0x140030275  mov     rdi, [rdx+30h]
0x140030279  mov     r15, [rdx+58h]
0x14003027d  mov     qword ptr [rsp+1100h+ActivityId.Data1], rax
0x140030282  mov     eax, [rdx+48h]
0x140030285  mov     dword ptr [rsp+1100h+var_10C0], 0
0x14003028d  mov     dword ptr [rsp+1100h+var_10C8], eax
0x140030291  mov     [rsp+1100h+var_10A0.Data1], r13d
0x140030296  mov     dword ptr [rsp+1100h+var_10A0.Data2], r12d
0x14003029b  mov     [rsp+1100h+var_10D0], cl
0x14003029f  test    eax, eax
0x1400302a1  jnz     loc_14003043C
0x1400302a7  mov     r14, qword ptr [rsp+1100h+var_10A0.Data1]
0x1400302ac  lea     rbx, [rdi+28F0h]
0x1400302b3  mov     rcx, rbx
0x1400302b6  call    VidLockAcquireExclusive
0x1400302bb  mov     r9, [rdi+2A08h]
0x1400302c2  mov     rcx, rbx
0x1400302c5  mov     rax, [r9+28h]
0x1400302c9  mov     [rsi], rax
0x1400302cc  mov     [r9+28h], rsi
0x1400302d0  call    VidLockRelease
0x1400302d5  xor     ecx, ecx
0x1400302d7  mov     r8, r15
0x1400302da  cmp     dword ptr [rsp+1100h+var_10C8], ecx
0x1400302de  jz      loc_14003045B
0x1400302e4  lea     rax, [rsp+1100h+var_10C0]
0x1400302e9  mov     r9d, r12d
0x1400302ec  mov     [rsp+1100h+var_10D8], rax
0x1400302f1  mov     edx, r13d
0x1400302f4  mov     byte ptr [rsp+1100h+UserData], cl
0x1400302f8  mov     rcx, rdi
0x1400302fb  call    VsmmHintApplyRange
0x140030300  xor     r15d, r15d
0x140030303  mov     ebx, eax
0x140030305  test    r14, r14
0x140030308  jz      short loc_140030315
0x14003030a  lea     rcx, [r14+8]
0x14003030e  xor     edx, edx
0x140030310  call    VidRefCounterDec
0x140030315  test    ebx, ebx
0x140030317  js      loc_140030476
0x14003031d  mov     r14, qword ptr [rsp+1100h+ActivityId.Data1]
0x140030322  mov     rcx, rdi
0x140030325  mov     r8, r14
0x140030328  call    VsmmEpfpCompletionDeliver
0x14003032d  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x140030334  test    rcx, rcx
0x140030337  jz      loc_14003040C
0x14003033d  lea     rdx, VID_EPF_FAULT_STOP; EventDescriptor
0x140030344  call    cs:__imp_EtwEventEnabled
0x14003034b  nop     dword ptr [rax+rax+00h]
0x140030350  test    al, al
0x140030352  jz      loc_14003040C
0x140030358  cmp     cs:VID_TRACE_ETW_GUID_Context, r15
0x14003035f  xorps   xmm0, xmm0
0x140030362  mov     rsi, [rdi+288h]
0x140030369  xorps   xmm1, xmm1
0x14003036c  movups  xmmword ptr [rsp+1100h+var_10A0.Data1], xmm0
0x140030371  movaps  xmmword ptr [rsp+1100h+ActivityId.Data1], xmm1
0x140030376  jz      short loc_140030393
0x140030378  lea     rdx, [rsp+1100h+ActivityId]; ActivityId
0x14003037d  mov     ecx, 1; ControlCode
0x140030382  call    cs:__imp_EtwActivityIdControl
0x140030389  nop     dword ptr [rax+rax+00h]
0x14003038e  movaps  xmm1, xmmword ptr [rsp+1100h+ActivityId.Data1]
0x140030393  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x14003039a  lea     r8, [rsp+1100h+var_10A0]; ActivityId
0x14003039f  movsxd  rax, ebx
0x1400303a2  lea     rdx, VID_EPF_FAULT_STOP; EventDescriptor
0x1400303a9  mov     [rsp+1100h+var_10C8], rax
0x1400303ae  mov     r9d, 3; UserDataCount
0x1400303b4  lea     rax, [rsp+1100h+ActivityId]
0x1400303b9  movdqa  xmmword ptr [rsp+1100h+var_10A0.Data1], xmm1
0x1400303bf  mov     [rbp+1000h+var_1080.Ptr], rax
0x1400303c3  lea     rax, [rsp+1100h+var_10C0]
0x1400303c8  mov     [rbp+1000h+var_1070], rax
0x1400303cc  lea     rax, [rsp+1100h+var_10C8]
0x1400303d1  mov     [rbp+1000h+var_1060], rax
0x1400303d5  lea     rax, [rbp+1000h+var_1080]
0x1400303d9  mov     [rsp+1100h+UserData], rax; UserData
0x1400303de  mov     [rsp+1100h+var_10C0], r14
0x1400303e3  mov     qword ptr [rsp+1100h+ActivityId.Data1], rsi
0x1400303e8  mov     qword ptr [rbp+1000h+var_1080.Size], 8
0x1400303f0  mov     [rbp+1000h+var_1068], 8
0x1400303f8  mov     [rbp+1000h+var_1058], 8
0x140030400  call    cs:__imp_EtwWrite
0x140030407  nop     dword ptr [rax+rax+00h]
0x14003040c  lea     rcx, [rdi+28F8h]
0x140030413  call    VidOpCtrlFinish
0x140030418  mov     rcx, [rbp+1000h+var_50]
0x14003041f  xor     rcx, rsp; StackCookie
0x140030422  call    __security_check_cookie
0x140030427  add     rsp, 10C8h
0x14003042e  pop     r15
0x140030430  pop     r14
0x140030432  pop     r13
0x140030434  pop     r12
0x140030436  pop     rdi
0x140030437  pop     rsi
0x140030438  pop     rbx
0x140030439  pop     rbp
0x14003043a  retn
0x14003043c  mov     r8, r12
0x14003043f  lea     rcx, [rbp+1000h+var_1050]; void *
0x140030443  shl     r8, 3; Size
0x140030447  xor     r14d, r14d
0x14003044a  mov     rdx, r15; Src
0x14003044d  call    memmove
0x140030452  lea     r15, [rbp+1000h+var_1050]
0x140030456  jmp     loc_1400302AC
0x14003045b  mov     r9b, [rsp+1100h+var_10D0]
0x140030460  mov     rdx, qword ptr [rsp+1100h+var_10A0.Data1]
0x140030465  mov     byte ptr [rsp+1100h+UserData], cl
0x140030469  mov     rcx, rdi
0x14003046c  call    VsmmHandleVaBackedMemoryIntercept
0x140030471  jmp     loc_140030300
0x140030476  mov     rax, [rdi+2A08h]
0x14003047d  lock add dword ptr [rax+30h], 4
0x140030482  jmp     loc_14003031D
```
