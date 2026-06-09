# NtOpenEnlistmentExt

- ea: `0x140012ff0`
- end: `0x14001325d`
- name: `NtOpenEnlistmentExt`
- size: `621`
- prototype: `NTSTATUS __stdcall(PHANDLE EnlistmentHandle, ACCESS_MASK DesiredAccess, HANDLE ResourceManagerHandle, LPGUID EnlistmentGuid, POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400014d4`
- `0x1400024e0`
- `0x14000d1fc`
- `0x14000d274`
- `0x140012ff0`
- `0x140019a30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140013209`
- `ntoskrnl!ObfDereferenceObject` at `0x140013223`
- `ntoskrnl!ObfDereferenceObject` at `0x1400220e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400220fe`
- `ntoskrnl!ObfDereferenceObject` at `0x140013209`
- `ntoskrnl!ObfDereferenceObject` at `0x140013223`
- `ntoskrnl!ObfDereferenceObject` at `0x1400220e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400220fe`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400131c6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400131c6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001315a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001315a`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022082`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022082`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400130ba`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400130ba`

## pseudocode

```c
NTSTATUS __stdcall NtOpenEnlistmentExt(
        PHANDLE EnlistmentHandle,
        ACCESS_MASK DesiredAccess,
        HANDLE ResourceManagerHandle,
        LPGUID EnlistmentGuid,
        POBJECT_ATTRIBUTES ObjectAttributes)
{
  ULONG Attributes; // r15d
  KPROCESSOR_MODE v10; // si
  __int64 ULong64FromUser; // rax
  int EnlistmentResourceManager; // ebx
  PVOID v14; // rdi
  PVOID Object; // [rsp+48h] [rbp-B0h] BYREF
  PVOID v16; // [rsp+50h] [rbp-A8h] BYREF
  int v17; // [rsp+58h] [rbp-A0h]
  PVOID v18; // [rsp+60h] [rbp-98h]
  void *Handle[5]; // [rsp+68h] [rbp-90h] BYREF
  GUID v20; // [rsp+90h] [rbp-68h] BYREF
  GUID v21; // [rsp+A0h] [rbp-58h] BYREF

  Handle[1] = EnlistmentHandle;
  LODWORD(Object) = DesiredAccess;
  Handle[2] = ResourceManagerHandle;
  v21 = 0;
  v16 = 0;
  Handle[0] = 0;
  if ( !DesiredAccess || !EnlistmentGuid )
    return -1073741811;
  v18 = 0;
  Attributes = 0;
  v17 = 0;
  v10 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v10 )
  {
    ULong64FromUser = RtlReadULong64FromUser(EnlistmentHandle);
    RtlWriteULong64ToUser(EnlistmentHandle, ULong64FromUser);
    v20 = 0;
    if ( ((unsigned __int8)EnlistmentGuid & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v20, EnlistmentGuid, 0x10u);
    v21 = v20;
  }
  else
  {
    v21 = *EnlistmentGuid;
    if ( ObjectAttributes )
      Attributes = ObjectAttributes->Attributes;
  }
  Object = 0;
  EnlistmentResourceManager = ObReferenceObjectByHandle(
                                ResourceManagerHandle,
                                1u,
                                (POBJECT_TYPE)TmResourceManagerObjectType,
                                v10,
                                &Object,
                                0);
  v14 = Object;
  v18 = Object;
  if ( EnlistmentResourceManager >= 0 )
  {
    EnlistmentResourceManager = TmpFindEnlistmentResourceManager(Object, &v21, &v16);
    if ( EnlistmentResourceManager >= 0 )
    {
      EnlistmentResourceManager = ObOpenObjectByPointer(
                                    v16,
                                    Attributes,
                                    0,
                                    DesiredAccess,
                                    (POBJECT_TYPE)TmEnlistmentObjectType,
                                    v10,
                                    Handle);
      if ( EnlistmentResourceManager >= 0 )
      {
        if ( v10 )
          RtlWriteULong64ToUser(EnlistmentHandle, Handle[0]);
        else
          *EnlistmentHandle = Handle[0];
      }
    }
  }
  if ( v14 )
    ObfDereferenceObject(v14);
  if ( v16 )
    ObfDereferenceObject(v16);
  return EnlistmentResourceManager;
}

```

## disassembly

```asm
0x140012ff0  push    rbx
0x140012ff2  push    rsi
0x140012ff3  push    rdi
0x140012ff4  push    r12
0x140012ff6  push    r13
0x140012ff8  push    r14
0x140012ffa  push    r15
0x140012ffc  sub     rsp, 0C0h
0x140013003  mov     rax, cs:__security_cookie
0x14001300a  xor     rax, rsp
0x14001300d  mov     [rsp+0F8h+var_48], rax
0x140013015  mov     rdi, r9
0x140013018  mov     r13, r8
0x14001301b  mov     r12d, edx
0x14001301e  mov     r14, rcx
0x140013021  mov     [rsp+0F8h+var_88], rcx
0x140013026  mov     dword ptr [rsp+0F8h+var_B0], edx
0x14001302a  mov     [rsp+0F8h+var_80], r8
0x14001302f  mov     rcx, [rsp+0F8h+ObjectAttributes]
0x140013037  xorps   xmm0, xmm0
0x14001303a  movups  [rsp+0F8h+var_58], xmm0
0x140013042  mov     [rsp+0F8h+var_A8], 0
0x14001304b  mov     [rsp+0F8h+var_90], 0
0x140013054  test    edx, edx
0x140013056  jz      loc_140013234
0x14001305c  test    r9, r9
0x14001305f  jz      loc_140013234
0x140013065  mov     [rsp+0F8h+var_98], 0
0x14001306e  xor     ebx, ebx
0x140013070  xor     r15d, r15d
0x140013073  mov     [rsp+0F8h+var_A0], r15d
0x140013078  mov     rax, gs:188h
0x140013081  mov     sil, [rax+232h]
0x140013088  mov     [rsp+0F8h+var_B8], sil
0x14001308d  test    sil, sil
0x140013090  jz      loc_140013116
0x140013096  mov     rcx, r14
0x140013099  call    RtlReadULong64FromUser
0x14001309e  mov     rdx, rax
0x1400130a1  mov     rcx, r14
0x1400130a4  call    RtlWriteULong64ToUser
0x1400130a9  xorps   xmm0, xmm0
0x1400130ac  movups  [rsp+0F8h+var_68], xmm0
0x1400130b4  test    dil, 3
0x1400130b8  jz      short loc_1400130C7
0x1400130ba  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400130c1  nop     dword ptr [rax+rax+00h]
0x1400130c6  int     3; Trap to Debugger
0x1400130c7  mov     r8d, 10h; Size
0x1400130cd  mov     rdx, rdi; Src
0x1400130d0  lea     rcx, [rsp+0F8h+var_68]; void *
0x1400130d8  call    RtlCopyFromUser
0x1400130dd  movaps  xmm0, [rsp+0F8h+var_68]
0x1400130e5  movdqa  [rsp+0F8h+var_58], xmm0
0x1400130ee  jmp     short loc_14001310B
0x1400130f0  mov     ebx, eax
0x1400130f2  mov     sil, [rsp+0F8h+var_B8]
0x1400130f7  mov     r15d, [rsp+0F8h+var_A0]
0x1400130fc  mov     r14, [rsp+0F8h+var_88]
0x140013101  mov     r12d, dword ptr [rsp+0F8h+var_B0]
0x140013106  mov     r13, [rsp+0F8h+var_80]
0x14001310b  test    ebx, ebx
0x14001310d  jns     short loc_14001312C
0x14001310f  mov     eax, ebx
0x140013111  jmp     loc_140013239
0x140013116  movups  xmm0, xmmword ptr [r9]
0x14001311a  movdqu  [rsp+0F8h+var_58], xmm0
0x140013123  test    rcx, rcx
0x140013126  jz      short loc_14001312C
0x140013128  mov     r15d, [rcx+18h]
0x14001312c  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x140013133  mov     [rsp+0F8h+var_B0], 0
0x14001313c  mov     [rsp+0F8h+HandleInformation], 0; HandleInformation
0x140013145  lea     rax, [rsp+0F8h+var_B0]
0x14001314a  mov     [rsp+0F8h+Object], rax; Object
0x14001314f  mov     r9b, sil; AccessMode
0x140013152  mov     edx, 1; DesiredAccess
0x140013157  mov     rcx, r13; Handle
0x14001315a  call    cs:__imp_ObReferenceObjectByHandle
0x140013161  nop     dword ptr [rax+rax+00h]
0x140013166  mov     ebx, eax
0x140013168  mov     rdi, [rsp+0F8h+var_B0]
0x14001316d  mov     [rsp+0F8h+var_98], rdi
0x140013172  mov     [rsp+0F8h+var_B4], eax
0x140013176  test    eax, eax
0x140013178  js      loc_140013201
0x14001317e  lea     r8, [rsp+0F8h+var_A8]
0x140013183  lea     rdx, [rsp+0F8h+var_58]
0x14001318b  mov     rcx, rdi
0x14001318e  call    TmpFindEnlistmentResourceManager
0x140013193  mov     ebx, eax
0x140013195  mov     [rsp+0F8h+var_B4], eax
0x140013199  test    eax, eax
0x14001319b  js      short loc_140013201
0x14001319d  lea     rax, [rsp+0F8h+var_90]
0x1400131a2  mov     [rsp+0F8h+Handle], rax; Handle
0x1400131a7  mov     byte ptr [rsp+0F8h+HandleInformation], sil; AccessMode
0x1400131ac  mov     rax, cs:TmEnlistmentObjectType
0x1400131b3  mov     [rsp+0F8h+Object], rax; ObjectType
0x1400131b8  mov     r9d, r12d; DesiredAccess
0x1400131bb  xor     r8d, r8d; PassedAccessState
0x1400131be  mov     edx, r15d; HandleAttributes
0x1400131c1  mov     rcx, [rsp+0F8h+var_A8]; Object
0x1400131c6  call    cs:__imp_ObOpenObjectByPointer
0x1400131cd  nop     dword ptr [rax+rax+00h]
0x1400131d2  mov     ebx, eax
0x1400131d4  mov     [rsp+0F8h+var_B4], eax
0x1400131d8  test    eax, eax
0x1400131da  js      short loc_140013201
0x1400131dc  mov     rax, [rsp+0F8h+var_90]
0x1400131e1  test    sil, sil
0x1400131e4  jz      short loc_1400131F3
0x1400131e6  mov     rdx, rax
0x1400131e9  mov     rcx, r14
0x1400131ec  call    RtlWriteULong64ToUser
0x1400131f1  jmp     short loc_1400131F6
0x1400131f3  mov     [r14], rax
0x1400131f6  jmp     short loc_140013201
0x1400131f8  mov     rdi, [rsp+0F8h+var_98]
0x1400131fd  mov     ebx, [rsp+0F8h+var_B4]
0x140013201  test    rdi, rdi
0x140013204  jz      short loc_140013215
0x140013206  mov     rcx, rdi; Object
0x140013209  call    cs:__imp_ObfDereferenceObject
0x140013210  nop     dword ptr [rax+rax+00h]
0x140013215  mov     rcx, [rsp+0F8h+var_A8]; Object
0x14001321a  test    rcx, rcx
0x14001321d  jz      loc_14001310F
0x140013223  call    cs:__imp_ObfDereferenceObject
0x14001322a  nop     dword ptr [rax+rax+00h]
0x14001322f  jmp     loc_14001310F
0x140013234  mov     eax, 0C000000Dh
0x140013239  mov     rcx, [rsp+0F8h+var_48]
0x140013241  xor     rcx, rsp; StackCookie
0x140013244  call    __security_check_cookie
0x140013249  add     rsp, 0C0h
0x140013250  pop     r15
0x140013252  pop     r14
0x140013254  pop     r13
0x140013256  pop     r12
0x140013258  pop     rdi
0x140013259  pop     rsi
0x14001325a  pop     rbx
0x14001325b  retn
0x140022079  push    rbp
0x14002207b  sub     rsp, 40h
0x14002207f  mov     rbp, rdx
0x140022082  call    cs:__imp_ExSystemExceptionFilter
0x140022089  nop     dword ptr [rax+rax+00h]
0x14002208e  nop
0x14002208f  add     rsp, 40h
0x140022093  pop     rbp
0x140022094  retn
0x140022096  push    rbp
0x140022098  sub     rsp, 40h
0x14002209c  mov     rbp, rdx
0x14002209f  mov     rax, gs:188h
0x1400220a8  mov     [rbp+80h], rax
0x1400220af  mov     rax, [rbp+80h]
0x1400220b6  mov     cl, [rax+232h]
0x1400220bc  mov     [rbp+41h], cl
0x1400220bf  mov     al, [rbp+41h]
0x1400220c2  xor     ecx, ecx
0x1400220c4  test    al, al
0x1400220c6  setnz   cl
0x1400220c9  mov     [rbp+5Ch], ecx
0x1400220cc  mov     eax, [rbp+5Ch]
0x1400220cf  add     rsp, 40h
0x1400220d3  pop     rbp
0x1400220d4  retn
0x1400220d6  push    rbp
0x1400220d8  sub     rsp, 40h
0x1400220dc  mov     rbp, rdx
0x1400220df  mov     rcx, [rbp+60h]; Object
0x1400220e3  test    rcx, rcx
0x1400220e6  jz      short loc_1400220F5
0x1400220e8  call    cs:__imp_ObfDereferenceObject
0x1400220ef  nop     dword ptr [rax+rax+00h]
0x1400220f4  nop
0x1400220f5  mov     rcx, [rbp+50h]; Object
0x1400220f9  test    rcx, rcx
0x1400220fc  jz      short loc_14002210B
0x1400220fe  call    cs:__imp_ObfDereferenceObject
0x140022105  nop     dword ptr [rax+rax+00h]
0x14002210a  nop
0x14002210b  add     rsp, 40h
0x14002210f  pop     rbp
0x140022110  retn
```
