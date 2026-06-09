# SP_QOS_CONTEXT::InitializeLimiterInternal(void)

- ea: `0x1400311ac`
- end: `0x140031382`
- name: `?InitializeLimiterInternal@SP_QOS_CONTEXT@@SAJXZ`
- size: `470`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140031ae4`

## callees

- `0x1400311ac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400312c2`
- `ntoskrnl!ExAllocatePool2` at `0x1400312c2`
- `ntoskrnl!KeInitializeQueue` at `0x1400311fa`
- `ntoskrnl!KeInitializeQueue` at `0x1400311fa`
- `ntoskrnl!PsCreateSystemThread` at `0x14003123e`
- `ntoskrnl!PsCreateSystemThread` at `0x14003123e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003127d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003127d`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400312a3`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400312a3`

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
0x1400311ac  mov     [rsp-8+arg_10], rbx
0x1400311b1  mov     [rsp-8+arg_18], rdi
0x1400311b6  push    rbp
0x1400311b7  mov     rbp, rsp
0x1400311ba  sub     rsp, 70h
0x1400311be  xorps   xmm0, xmm0
0x1400311c1  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400311c9  mov     edx, 1; Count
0x1400311ce  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x1400311d6  lea     rcx, Queue; Queue
0x1400311dd  mov     [rbp+ThreadHandle], 0
0x1400311e5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400311ea  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400311f2  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1400311fa  call    cs:__imp_KeInitializeQueue
0x140031201  nop     dword ptr [rax+rax+00h]
0x140031206  lea     rax, Object
0x14003120d  mov     cs:byte_14007F5C8, 1
0x140031214  mov     [rsp+70h+StartContext], rax; StartContext
0x140031219  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003121d  lea     rax, ?SpLimiterDispatcherThreadRoutine@@YAXPEAX@Z; SpLimiterDispatcherThreadRoutine(void *)
0x140031224  xor     r9d, r9d; ProcessHandle
0x140031227  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x14003122c  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140031230  mov     edx, 1FFFFFh; DesiredAccess
0x140031235  mov     [rsp+70h+ClientId], 0; ClientId
0x14003123e  call    cs:__imp_PsCreateSystemThread
0x140031245  nop     dword ptr [rax+rax+00h]
0x14003124a  mov     ebx, eax
0x14003124c  test    eax, eax
0x14003124e  js      loc_14003136D
0x140031254  mov     rcx, [rbp+ThreadHandle]; Handle
0x140031258  lea     rax, [rbp+Object]
0x14003125c  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x140031265  xor     r9d, r9d; AccessMode
0x140031268  xor     r8d, r8d; ObjectType
0x14003126b  mov     [rsp+70h+ClientId], rax; Object
0x140031270  mov     edx, 100020h; DesiredAccess
0x140031275  mov     [rbp+Object], 0
0x14003127d  call    cs:__imp_ObReferenceObjectByHandle
0x140031284  nop     dword ptr [rax+rax+00h]
0x140031289  mov     ebx, eax
0x14003128b  mov     rax, [rbp+Object]
0x14003128f  mov     cs:Object, rax
0x140031296  test    ebx, ebx
0x140031298  js      loc_14003136D
0x14003129e  mov     ecx, 0FFFFh; GroupNumber
0x1400312a3  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400312aa  nop     dword ptr [rax+rax+00h]
0x1400312af  mov     edx, eax
0x1400312b1  mov     ecx, 48h ; 'H'
0x1400312b6  shl     rdx, 6
0x1400312ba  mov     r8d, 614C7053h
0x1400312c0  mov     edi, eax
0x1400312c2  call    cs:__imp_ExAllocatePool2
0x1400312c9  nop     dword ptr [rax+rax+00h]
0x1400312ce  mov     cs:P, rax
0x1400312d5  test    rax, rax
0x1400312d8  jnz     short loc_1400312E4
0x1400312da  mov     ebx, 0C000009Ah
0x1400312df  jmp     loc_14003136D
0x1400312e4  xor     r8d, r8d
0x1400312e7  test    edi, edi
0x1400312e9  jz      short loc_140031330
0x1400312eb  xor     r9d, r9d
0x1400312ee  mov     rcx, cs:P
0x1400312f5  lea     rax, ?IrpDispatcherWorkItemRoutine@SP_QOS_CONTEXT@@SAXPEAX@Z; SP_QOS_CONTEXT::IrpDispatcherWorkItemRoutine(void *)
0x1400312fc  mov     rdx, r9
0x1400312ff  inc     r8d
0x140031302  shl     rdx, 6
0x140031306  inc     r9
0x140031309  add     rcx, rdx
0x14003130c  mov     [rcx+18h], rax
0x140031310  mov     [rcx+20h], rcx
0x140031314  mov     qword ptr [rcx+8], 0
0x14003131c  mov     rax, cs:P
0x140031323  mov     qword ptr [rdx+rax], 0
0x14003132b  cmp     r8d, edi
0x14003132e  jb      short loc_1400312EE
0x140031330  mov     cs:dword_14007F570, 2000h
0x14003133a  xor     eax, eax
0x14003133c  mov     ecx, 1000h
0x140031341  inc     eax
0x140031343  shr     ecx, 1
0x140031345  jnz     short loc_140031341
0x140031347  mov     cs:dword_14007F574, eax
0x14003134d  mov     cs:dword_14007F578, 1
0x140031357  mov     cs:?SpQosGlobal@@3U_SP_QOS_GLOBALS@@A, 989680h; _SP_QOS_GLOBALS SpQosGlobal
0x140031362  mov     cs:qword_14007F568, 186A0h
0x14003136d  lea     r11, [rsp+70h+var_s0]
0x140031372  mov     eax, ebx
0x140031374  mov     rbx, [r11+20h]
0x140031378  mov     rdi, [r11+28h]
0x14003137c  mov     rsp, r11
0x14003137f  pop     rbp
0x140031380  retn
```
