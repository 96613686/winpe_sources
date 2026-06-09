# CGenericUSB::IoCtlCompletionSubmitUrb(WDFREQUEST__ *,_WDF_REQUEST_COMPLETION_PARAMS *)

- ea: `0x140001d10`
- end: `0x140001f84`
- name: `?IoCtlCompletionSubmitUrb@CGenericUSB@@QEAAXPEAUWDFREQUEST__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z`
- size: `628`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003bf0`

## callees

- `0x140001d10`
- `0x140003964`
- `0x1400039b8`
- `0x140006370`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlCompletionSubmitUrb(
        CGenericUSB *this,
        struct WDFREQUEST__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3)
{
  _QWORD *v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  NTSTATUS Status; // ebp
  __int64 v14; // r9
  int v15; // ecx
  unsigned int v16; // [rsp+80h] [rbp+8h] BYREF
  __int64 v17; // [rsp+98h] [rbp+20h] BYREF

  v16 = 0;
  v17 = 0;
  v6 = (_QWORD *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                   WPP_MAIN_CB.Queue.ListEntry.Blink,
                   a2,
                   off_140009018);
  v7 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[97].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         v6[221],
         &v17);
  v8 = v6[217];
  ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    *((_QWORD *)this + 10));
  v9 = *v6;
  if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v10 = (_QWORD *)v6[1], (_QWORD *)*v10 != v6) )
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
  ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    *((_QWORD *)this + 10));
  Status = a3->IoStatus.Status;
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, v11, v12, *(unsigned __int16 *)(v6[217] + 2LL), Status);
    *(_WORD *)v7 = 8;
    v15 = -1073704960;
    if ( *(int *)(v8 + 4) < 0 )
      v15 = *(_DWORD *)(v8 + 4);
    v14 = 0;
    *(_DWORD *)(v7 + 4) = v15;
  }
  else
  {
    if ( *(_WORD *)(v8 + 2) != *(_WORD *)(v7 + 2)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 40, &WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
    }
    if ( *(int *)(v8 + 4) < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 41, &WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
    }
    ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      *(_QWORD *)this);
    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD, __int64, _DWORD, unsigned int *))(v6[5] + 8LL))(
      v6 + 5,
      *((_QWORD *)this + 7),
      *((_QWORD *)this + 5),
      *((_QWORD *)this + 6),
      v7,
      v17,
      &v16);
    ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      *(_QWORD *)this);
    v14 = v16;
  }
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)Status,
    v14);
}

```

## disassembly

```asm
0x140001d10  mov     rax, rsp
0x140001d13  mov     [rax+10h], rbx
0x140001d17  push    rbp
0x140001d18  push    rsi
0x140001d19  push    rdi
0x140001d1a  push    r12
0x140001d1c  push    r13
0x140001d1e  push    r14
0x140001d20  push    r15
0x140001d22  sub     rsp, 40h
0x140001d26  mov     dword ptr [rax+8], 0
0x140001d2d  mov     rbp, r8
0x140001d30  mov     r8, cs:off_140009018
0x140001d37  mov     r15, rcx
0x140001d3a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001d41  mov     r13, rdx
0x140001d44  mov     qword ptr [rax+20h], 0
0x140001d4c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001d53  mov     rax, [rax+650h]
0x140001d5a  call    _guard_dispatch_icall
0x140001d5f  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue
0x140001d66  lea     r8, [rsp+78h+arg_18]
0x140001d6e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001d75  mov     rdi, rax
0x140001d78  mov     rax, [rdx+610h]
0x140001d7f  mov     rdx, [rdi+6E8h]
0x140001d86  call    _guard_dispatch_icall
0x140001d8b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140001d92  mov     r14, rax
0x140001d95  mov     rdx, [r15+50h]
0x140001d99  mov     rsi, [rdi+6C8h]
0x140001da0  mov     rax, [rcx+9E0h]
0x140001da7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001dae  call    _guard_dispatch_icall
0x140001db3  mov     rcx, [rdi]
0x140001db6  cmp     [rcx+8], rdi
0x140001dba  jnz     loc_140001F7D
0x140001dc0  mov     rax, [rdi+8]
0x140001dc4  cmp     [rax], rdi
0x140001dc7  jnz     loc_140001F7D
0x140001dcd  mov     [rax], rcx
0x140001dd0  mov     [rcx+8], rax
0x140001dd4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001ddb  mov     rdx, [r15+50h]
0x140001ddf  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001de6  mov     rax, [rax+9E8h]
0x140001ded  call    _guard_dispatch_icall
0x140001df2  mov     ebp, [rbp+8]
0x140001df5  lea     rbx, WPP_GLOBAL_Control
0x140001dfc  test    ebp, ebp
0x140001dfe  js      loc_140001EFF
0x140001e04  movzx   edx, word ptr [r14+2]
0x140001e09  cmp     [rsi+2], dx
0x140001e0d  jz      short loc_140001E4A
0x140001e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e16  cmp     rcx, rbx
0x140001e19  jz      short loc_140001E4A
0x140001e1b  cmp     byte ptr [rcx+29h], 2
0x140001e1f  jb      short loc_140001E4A
0x140001e21  mov     rax, [rdi+6C8h]
0x140001e28  mov     r9d, edx
0x140001e2b  mov     rcx, [rcx+18h]
0x140001e2f  mov     edx, 28h ; '('
0x140001e34  movzx   r8d, word ptr [rax+2]
0x140001e39  mov     dword ptr [rsp+78h+var_58], r8d
0x140001e3e  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140001e45  call    WPP_SF_DD
0x140001e4a  mov     eax, [rsi+4]
0x140001e4d  test    eax, eax
0x140001e4f  jns     short loc_140001E81
0x140001e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e58  cmp     rcx, rbx
0x140001e5b  jz      short loc_140001E81
0x140001e5d  cmp     byte ptr [rcx+29h], 2
0x140001e61  jb      short loc_140001E81
0x140001e63  movzx   r9d, word ptr [rsi+2]
0x140001e68  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140001e6f  mov     rcx, [rcx+18h]
0x140001e73  mov     edx, 29h ; ')'
0x140001e78  mov     dword ptr [rsp+78h+var_58], eax
0x140001e7c  call    WPP_SF_DD
0x140001e81  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001e88  mov     rdx, [r15]
0x140001e8b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001e92  mov     rax, [rax+9B0h]
0x140001e99  call    _guard_dispatch_icall
0x140001e9e  mov     edx, dword ptr [rsp+78h+arg_18]
0x140001ea5  lea     rcx, [rsp+78h+arg_0]
0x140001ead  mov     rax, [rdi+28h]
0x140001eb1  mov     r9, [r15+30h]
0x140001eb5  mov     r8, [r15+28h]
0x140001eb9  mov     [rsp+78h+var_48], rcx
0x140001ebe  lea     rcx, [rdi+28h]
0x140001ec2  mov     rax, [rax+8]
0x140001ec6  mov     [rsp+78h+var_50], edx
0x140001eca  mov     rdx, [r15+38h]
0x140001ece  mov     [rsp+78h+var_58], r14
0x140001ed3  call    _guard_dispatch_icall
0x140001ed8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001edf  mov     rdx, [r15]
0x140001ee2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001ee9  mov     rax, [rax+9B8h]
0x140001ef0  call    _guard_dispatch_icall
0x140001ef5  mov     r9d, [rsp+78h+arg_0]
0x140001efd  jmp     short loc_140001F44
0x140001eff  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f06  cmp     rcx, rbx
0x140001f09  jz      short loc_140001F2A
0x140001f0b  cmp     byte ptr [rcx+29h], 2
0x140001f0f  jb      short loc_140001F2A
0x140001f11  mov     rax, [rdi+6C8h]
0x140001f18  mov     rcx, [rcx+18h]
0x140001f1c  mov     dword ptr [rsp+78h+var_58], ebp
0x140001f20  movzx   r9d, word ptr [rax+2]
0x140001f25  call    WPP_SF_Dd
0x140001f2a  mov     word ptr [r14], 8
0x140001f30  mov     ecx, 0C0009000h
0x140001f35  mov     eax, [rsi+4]
0x140001f38  test    eax, eax
0x140001f3a  cmovs   ecx, eax
0x140001f3d  xor     r9d, r9d
0x140001f40  mov     [r14+4], ecx
0x140001f44  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001f4b  mov     r8d, ebp
0x140001f4e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001f55  mov     rdx, r13
0x140001f58  mov     rax, [rax+848h]
0x140001f5f  call    _guard_dispatch_icall
0x140001f64  mov     rbx, [rsp+78h+arg_8]
0x140001f6c  add     rsp, 40h
0x140001f70  pop     r15
0x140001f72  pop     r14
0x140001f74  pop     r13
0x140001f76  pop     r12
0x140001f78  pop     rdi
0x140001f79  pop     rsi
0x140001f7a  pop     rbp
0x140001f7b  retn
0x140001f7d  mov     ecx, 3
0x140001f82  int     29h; Win8: RtlFailFast(ecx)
```
