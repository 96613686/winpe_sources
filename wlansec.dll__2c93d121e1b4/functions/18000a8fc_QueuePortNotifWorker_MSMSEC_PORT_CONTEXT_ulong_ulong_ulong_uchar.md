# QueuePortNotifWorker(MSMSEC_PORT_CONTEXT *,ulong,ulong,ulong,uchar *)

- ea: `0x18000a8fc`
- end: `0x18000aae6`
- name: `?QueuePortNotifWorker@@YAKPEAUMSMSEC_PORT_CONTEXT@@KKKPEAE@Z`
- size: `490`
- prototype: `unsigned int(struct MSMSEC_PORT_CONTEXT *, unsigned int, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bc44`
- `0x18001ccb0`
- `0x180074048`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a8fc`
- `0x18000acfc`
- `0x18000b348`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000a9b7`
- `MobileNetworking!ReleaseWriteLock` at `0x18000a9b7`
- `MobileNetworking!AcquireWriteLock` at `0x18000a95c`
- `MobileNetworking!AcquireWriteLock` at `0x18000a95c`

## pseudocode

```c
__int64 __fastcall QueuePortNotifWorker(
        struct MSMSEC_PORT_CONTEXT *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned __int8 *a5)
{
  PVOID *v8; // rcx
  struct _GUID *v9; // rbx
  void *v10; // rcx
  int v11; // r8d
  void *v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  unsigned int v17; // [rsp+20h] [rbp-68h]
  size_t Size; // [rsp+30h] [rbp-58h]
  struct _GUID v19; // [rsp+40h] [rbp-48h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v8[7], 11, a3, *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), (__int64)">>> Locking >>>");
  }
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "QueuePortNotifWorker", 168);
  v9 = (struct _GUID *)*((_QWORD *)a1 + 3);
  v10 = *(void **)v9[164].Data4;
  v19 = v9[2];
  SecMgrCorrelateToSession(v10);
  v12 = *(void **)v9[164].Data4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      v11,
      *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL),
      (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "QueuePortNotifWorker", 171);
  LODWORD(Size) = a4;
  v13 = QueueNotifWorker(
          *((void **)a1 + 4),
          v12,
          &v19,
          *((unsigned int (**)(void *, void *, struct _L2_NOTIFICATION_DATA *))a1 + 13),
          v17,
          a3,
          Size,
          a5);
  v14 = v13;
  if ( !v13 )
    goto LABEL_11;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids, v13);
LABEL_11:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x100) != 0 )
    WPP_SF_d(v15[7], 24, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18000a8fc  push    rbx
0x18000a8fe  push    rbp
0x18000a8ff  push    rsi
0x18000a900  push    rdi
0x18000a901  push    r14
0x18000a903  push    r15
0x18000a905  sub     rsp, 58h
0x18000a909  mov     esi, r9d
0x18000a90c  mov     ebp, r8d
0x18000a90f  mov     rdi, rcx
0x18000a912  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a919  lea     r14, WPP_GLOBAL_Control
0x18000a920  mov     r15d, 100h
0x18000a926  cmp     rcx, r14
0x18000a929  jz      short loc_18000A944
0x18000a92b  test    [rcx+44h], r15d
0x18000a92f  jnz     loc_18000AA1D
0x18000a935  cmp     rcx, r14
0x18000a938  jz      short loc_18000A944
0x18000a93a  test    [rcx+44h], r15d
0x18000a93e  jnz     loc_18000AA3E
0x18000a944  mov     rcx, [rdi+18h]
0x18000a948  lea     r8, aQueueportnotif; "QueuePortNotifWorker"
0x18000a94f  mov     r9d, 0A8h
0x18000a955  lea     rdx, [rcx+9D0h]
0x18000a95c  call    cs:__imp_AcquireWriteLock
0x18000a963  nop     dword ptr [rax+rax+00h]
0x18000a968  mov     rbx, [rdi+18h]
0x18000a96c  movups  xmm0, xmmword ptr [rbx+20h]
0x18000a970  mov     rcx, [rbx+0A48h]; void *
0x18000a977  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x18000a97d  call    ?SecMgrCorrelateToSession@@YAXPEAX@Z; SecMgrCorrelateToSession(void *)
0x18000a982  mov     rbx, [rbx+0A48h]
0x18000a989  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a990  cmp     rcx, r14
0x18000a993  jz      short loc_18000A99F
0x18000a995  test    [rcx+44h], r15d
0x18000a999  jnz     loc_18000AA68
0x18000a99f  mov     rcx, [rdi+18h]
0x18000a9a3  lea     r8, aQueueportnotif; "QueuePortNotifWorker"
0x18000a9aa  mov     r9d, 0ABh
0x18000a9b0  lea     rdx, [rcx+9D0h]
0x18000a9b7  call    cs:__imp_ReleaseWriteLock
0x18000a9be  nop     dword ptr [rax+rax+00h]
0x18000a9c3  mov     rax, [rsp+88h+arg_20]
0x18000a9cb  lea     r8, [rsp+88h+var_48]; struct _GUID *
0x18000a9d0  mov     r9, [rdi+68h]; unsigned int (*)(void *, void *, struct _L2_NOTIFICATION_DATA *)
0x18000a9d4  mov     rdx, rbx; void *
0x18000a9d7  mov     rcx, [rdi+20h]; void *
0x18000a9db  mov     [rsp+88h+var_50], rax; unsigned __int8 *
0x18000a9e0  mov     dword ptr [rsp+88h+Size], esi; Size
0x18000a9e4  mov     [rsp+88h+var_60], ebp; unsigned int
0x18000a9e8  call    ?QueueNotifWorker@@YAKPEAX0PEAU_GUID@@P6AK00PEAU_L2_NOTIFICATION_DATA@@@ZKKKPEAE@Z; QueueNotifWorker(void *,void *,_GUID *,ulong (*)(void *,void *,_L2_NOTIFICATION_DATA *),ulong,ulong,ulong,uchar *)
0x18000a9ed  mov     ebx, eax
0x18000a9ef  test    eax, eax
0x18000a9f1  jnz     loc_18000AA92
0x18000a9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9fe  cmp     rcx, r14
0x18000aa01  jz      short loc_18000AA0D
0x18000aa03  test    [rcx+44h], r15d
0x18000aa07  jnz     loc_18000AAC9
0x18000aa0d  mov     eax, ebx
0x18000aa0f  add     rsp, 58h
0x18000aa13  pop     r15
0x18000aa15  pop     r14
0x18000aa17  pop     rdi
0x18000aa18  pop     rsi
0x18000aa19  pop     rbp
0x18000aa1a  pop     rbx
0x18000aa1b  retn
0x18000aa1d  mov     rcx, [rcx+38h]
0x18000aa21  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x18000aa28  mov     edx, 16h
0x18000aa2d  call    WPP_SF_
0x18000aa32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa39  jmp     loc_18000A935
0x18000aa3e  mov     r9, [rdi+18h]
0x18000aa42  lea     rax, aLocking; ">>> Locking >>>"
0x18000aa49  mov     rcx, [rcx+38h]
0x18000aa4d  mov     edx, 0Bh
0x18000aa52  mov     [rsp+88h+var_68], rax
0x18000aa57  mov     r9d, [r9+9C0h]
0x18000aa5e  call    WPP_SF_Ls
0x18000aa63  jmp     loc_18000A944
0x18000aa68  mov     r9, [rdi+18h]
0x18000aa6c  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18000aa73  mov     rcx, [rcx+38h]
0x18000aa77  mov     edx, 0Bh
0x18000aa7c  mov     [rsp+88h+var_68], rax
0x18000aa81  mov     r9d, [r9+9C0h]
0x18000aa88  call    WPP_SF_Ls
0x18000aa8d  jmp     loc_18000A99F
0x18000aa92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa99  cmp     rcx, r14
0x18000aa9c  jz      loc_18000AA0D
0x18000aaa2  test    byte ptr [rcx+44h], 1
0x18000aaa6  jz      loc_18000A9FE
0x18000aaac  mov     rcx, [rcx+38h]
0x18000aab0  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x18000aab7  mov     edx, 17h
0x18000aabc  mov     r9d, ebx
0x18000aabf  call    WPP_SF_d
0x18000aac4  jmp     loc_18000A9F7
0x18000aac9  mov     rcx, [rcx+38h]
0x18000aacd  lea     r8, WPP_eb0293db2dec3d3d7bc787c639a8dbbf_Traceguids
0x18000aad4  mov     edx, 18h
0x18000aad9  mov     r9d, ebx
0x18000aadc  call    WPP_SF_d
0x18000aae1  jmp     loc_18000AA0D
```
