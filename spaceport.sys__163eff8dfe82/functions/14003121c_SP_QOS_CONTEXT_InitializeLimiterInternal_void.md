# SP_QOS_CONTEXT::InitializeLimiterInternal(void)

- ea: `0x14003121c`
- end: `0x1400313f2`
- name: `?InitializeLimiterInternal@SP_QOS_CONTEXT@@SAJXZ`
- size: `470`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140031b54`

## callees

- `0x14003121c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140031332`
- `ntoskrnl!ExAllocatePool2` at `0x140031332`
- `ntoskrnl!KeInitializeQueue` at `0x14003126a`
- `ntoskrnl!KeInitializeQueue` at `0x14003126a`
- `ntoskrnl!PsCreateSystemThread` at `0x1400312ae`
- `ntoskrnl!PsCreateSystemThread` at `0x1400312ae`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400312ed`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400312ed`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140031313`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140031313`

## pseudocode

```c
__int64 SP_QOS_CONTEXT::InitializeLimiterInternal(void)
{
  NTSTATUS v0; // ebx
  ULONG MaximumProcessorCount; // edi
  ULONG v2; // r8d
  __int64 v3; // r9
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  int v6; // eax
  unsigned int v7; // ecx
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+10h] BYREF
  PVOID Object; // [rsp+88h] [rbp+18h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ThreadHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  KeInitializeQueue(&Queue, 1u);
  byte_14007F5C8 = 1;
  v0 = PsCreateSystemThread(
         &ThreadHandle,
         0x1FFFFFu,
         &ObjectAttributes,
         0,
         0,
         (PKSTART_ROUTINE)SpLimiterDispatcherThreadRoutine,
         &::Object);
  if ( v0 >= 0 )
  {
    Object = 0;
    v0 = ObReferenceObjectByHandle(ThreadHandle, 0x100020u, 0, 0, &Object, 0);
    ::Object = Object;
    if ( v0 >= 0 )
    {
      MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
      P = (PVOID)ExAllocatePool2(72, (unsigned __int64)MaximumProcessorCount << 6, 1632399443);
      if ( P )
      {
        v2 = 0;
        if ( MaximumProcessorCount )
        {
          v3 = 0;
          do
          {
            ++v2;
            v4 = v3++ << 6;
            v5 = (char *)P + v4;
            v5[3] = SP_QOS_CONTEXT::IrpDispatcherWorkItemRoutine;
            v5[4] = v5;
            v5[1] = 0;
            *(_QWORD *)((char *)P + v4) = 0;
          }
          while ( v2 < MaximumProcessorCount );
        }
        dword_14007F570 = 0x2000;
        v6 = 0;
        v7 = 4096;
        do
        {
          ++v6;
          v7 >>= 1;
        }
        while ( v7 );
        dword_14007F574 = v6;
        dword_14007F578 = 1;
        SpQosGlobal = 10000000;
        qword_14007F568 = 100000;
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14003121c  mov     [rsp-8+arg_10], rbx
0x140031221  mov     [rsp-8+arg_18], rdi
0x140031226  push    rbp
0x140031227  mov     rbp, rsp
0x14003122a  sub     rsp, 70h
0x14003122e  xorps   xmm0, xmm0
0x140031231  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140031239  mov     edx, 1; Count
0x14003123e  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x140031246  lea     rcx, Queue; Queue
0x14003124d  mov     [rbp+ThreadHandle], 0
0x140031255  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003125a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140031262  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14003126a  call    cs:__imp_KeInitializeQueue
0x140031271  nop     dword ptr [rax+rax+00h]
0x140031276  lea     rax, Object
0x14003127d  mov     cs:byte_14007F5C8, 1
0x140031284  mov     [rsp+70h+StartContext], rax; StartContext
0x140031289  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003128d  lea     rax, ?SpLimiterDispatcherThreadRoutine@@YAXPEAX@Z; SpLimiterDispatcherThreadRoutine(void *)
0x140031294  xor     r9d, r9d; ProcessHandle
0x140031297  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14003129c  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400312a0  mov     edx, 1FFFFFh; DesiredAccess
0x1400312a5  mov     [rsp+70h+ClientId], 0; ClientId
0x1400312ae  call    cs:__imp_PsCreateSystemThread
0x1400312b5  nop     dword ptr [rax+rax+00h]
0x1400312ba  mov     ebx, eax
0x1400312bc  test    eax, eax
0x1400312be  js      loc_1400313DD
0x1400312c4  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400312c8  lea     rax, [rbp+Object]
0x1400312cc  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x1400312d5  xor     r9d, r9d; AccessMode
0x1400312d8  xor     r8d, r8d; ObjectType
0x1400312db  mov     [rsp+70h+ClientId], rax; Object
0x1400312e0  mov     edx, 100020h; DesiredAccess
0x1400312e5  mov     [rbp+Object], 0
0x1400312ed  call    cs:__imp_ObReferenceObjectByHandle
0x1400312f4  nop     dword ptr [rax+rax+00h]
0x1400312f9  mov     ebx, eax
0x1400312fb  mov     rax, [rbp+Object]
0x1400312ff  mov     cs:Object, rax
0x140031306  test    ebx, ebx
0x140031308  js      loc_1400313DD
0x14003130e  mov     ecx, 0FFFFh; GroupNumber
0x140031313  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14003131a  nop     dword ptr [rax+rax+00h]
0x14003131f  mov     edx, eax
0x140031321  mov     ecx, 48h ; 'H'
0x140031326  shl     rdx, 6
0x14003132a  mov     r8d, 614C7053h
0x140031330  mov     edi, eax
0x140031332  call    cs:__imp_ExAllocatePool2
0x140031339  nop     dword ptr [rax+rax+00h]
0x14003133e  mov     cs:P, rax
0x140031345  test    rax, rax
0x140031348  jnz     short loc_140031354
0x14003134a  mov     ebx, 0C000009Ah
0x14003134f  jmp     loc_1400313DD
0x140031354  xor     r8d, r8d
0x140031357  test    edi, edi
0x140031359  jz      short loc_1400313A0
0x14003135b  xor     r9d, r9d
0x14003135e  mov     rcx, cs:P
0x140031365  lea     rax, ?IrpDispatcherWorkItemRoutine@SP_QOS_CONTEXT@@SAXPEAX@Z; SP_QOS_CONTEXT::IrpDispatcherWorkItemRoutine(void *)
0x14003136c  mov     rdx, r9
0x14003136f  inc     r8d
0x140031372  shl     rdx, 6
0x140031376  inc     r9
0x140031379  add     rcx, rdx
0x14003137c  mov     [rcx+18h], rax
0x140031380  mov     [rcx+20h], rcx
0x140031384  mov     qword ptr [rcx+8], 0
0x14003138c  mov     rax, cs:P
0x140031393  mov     qword ptr [rdx+rax], 0
0x14003139b  cmp     r8d, edi
0x14003139e  jb      short loc_14003135E
0x1400313a0  mov     cs:dword_14007F570, 2000h
0x1400313aa  xor     eax, eax
0x1400313ac  mov     ecx, 1000h
0x1400313b1  inc     eax
0x1400313b3  shr     ecx, 1
0x1400313b5  jnz     short loc_1400313B1
0x1400313b7  mov     cs:dword_14007F574, eax
0x1400313bd  mov     cs:dword_14007F578, 1
0x1400313c7  mov     cs:?SpQosGlobal@@3U_SP_QOS_GLOBALS@@A, 989680h; _SP_QOS_GLOBALS SpQosGlobal
0x1400313d2  mov     cs:qword_14007F568, 186A0h
0x1400313dd  lea     r11, [rsp+70h+var_s0]
0x1400313e2  mov     eax, ebx
0x1400313e4  mov     rbx, [r11+20h]
0x1400313e8  mov     rdi, [r11+28h]
0x1400313ec  mov     rsp, r11
0x1400313ef  pop     rbp
0x1400313f0  retn
```
