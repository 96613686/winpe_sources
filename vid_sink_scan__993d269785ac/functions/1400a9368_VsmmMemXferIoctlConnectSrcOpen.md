# VsmmMemXferIoctlConnectSrcOpen

- ea: `0x1400a9368`
- end: `0x1400a95a2`
- name: `VsmmMemXferIoctlConnectSrcOpen`
- size: `570`
- prototype: `__int64 __fastcall(PVOID P, HANDLE Handle, KPROCESSOR_MODE AccessMode)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x14000fac8`
- `0x14000fbc4`
- `0x14002f524`
- `0x1400a9368`
- `0x1400a9634`
- `0x1400a9764`
- `0x1400f2e2c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a93b0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a93b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a9568`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a9568`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a9453`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a9453`
- `ntoskrnl!IoFileObjectType` at `0x1400a9386`
- `ntoskrnl!IoFileObjectType` at `0x1400a9438`
- `ntoskrnl!ZwClose` at `0x1400a9554`
- `ntoskrnl!ZwClose` at `0x1400a9554`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400a93eb`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400a93eb`

## string_xrefs

- `0x1400a93d7`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400a9414`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400a9475`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400a94b0`: `VsmmMemXferIoctlConnectSrcOpen`
- `0x1400a9517`: `VsmmMemXferIoctlConnectSrcOpen`

## pseudocode

```c
__int64 __fastcall VsmmMemXferIoctlConnectSrcOpen(char *P, HANDLE Handle, KPROCESSOR_MODE AccessMode)
{
  _QWORD *v4; // rbx
  NTSTATUS v5; // eax
  PFILE_OBJECT v6; // rsi
  NTSTATUS v7; // edi
  __int64 v8; // rdx
  PDEVICE_OBJECT RelatedDeviceObject; // r14
  __int64 v10; // rax
  HANDLE v11; // rax
  PFILE_OBJECT FileObject; // [rsp+40h] [rbp-28h] BYREF
  HANDLE v14; // [rsp+88h] [rbp+20h] BYREF

  v14 = (HANDLE)-1LL;
  v4 = 0;
  FileObject = 0;
  v5 = ObReferenceObjectByHandle(Handle, 0x82u, (POBJECT_TYPE)IoFileObjectType, AccessMode, (PVOID *)&FileObject, 0);
  v6 = FileObject;
  v7 = v5;
  if ( v5 >= 0 )
  {
    RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
    if ( RelatedDeviceObject )
    {
      v7 = ObOpenObjectByPointer(v6, 0x200u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &v14);
      if ( v7 >= 0 )
      {
        v10 = VsmmMemXferpConnectionAlloc(P, 1);
        v4 = (_QWORD *)v10;
        if ( v10 )
        {
          *(_DWORD *)(v10 + 116) = 1;
          *(_DWORD *)(v10 + 112) = 2;
          v11 = v14;
          v4[17] = RelatedDeviceObject;
          v4[15] = v11;
          v4[16] = v6;
          VidAutoExpandPushLockAcquireExclusive(P + 8608);
          if ( *((_QWORD *)P + 1078) )
          {
            v7 = -1073741436;
            VidTraceErrorStatusInternal0(
              "VsmmMemXferIoctlConnectSrcOpen",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
              984);
          }
          else
          {
            *((_QWORD *)P + 1078) = v4;
            v6 = 0;
            v4 = 0;
            v14 = (HANDLE)-1LL;
            v7 = 0;
          }
          VidAutoExpandPushLockReleaseExclusive(P + 8608);
        }
        else
        {
          v7 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmMemXferIoctlConnectSrcOpen",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
            965);
        }
      }
      else
      {
        VidTraceErrorStatusInternal0(
          "VsmmMemXferIoctlConnectSrcOpen",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c",
          951);
      }
    }
    else
    {
      v7 = -1073741811;
      VidTraceErrorStatusInternal0("VsmmMemXferIoctlConnectSrcOpen", "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c", 928);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0("VsmmMemXferIoctlConnectSrcOpen", "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c", 916);
  }
  if ( v14 != (HANDLE)-1LL )
    ZwClose(v14);
  if ( v6 )
    ObfDereferenceObject(v6);
  if ( v4 )
  {
    LOBYTE(v8) = 1;
    VidOpCtrlBlock(v4 + 2, v8);
    VsmmMemXferpConnectionFreeInternal(v4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400a9368  mov     r11, rsp
0x1400a936b  mov     [r11+8], rbx
0x1400a936f  mov     [r11+10h], rbp
0x1400a9373  push    rsi
0x1400a9374  push    rdi
0x1400a9375  push    r14
0x1400a9377  sub     rsp, 50h
0x1400a937b  mov     r9b, r8b; AccessMode
0x1400a937e  mov     qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x1400a9386  mov     r8, cs:__imp_IoFileObjectType
0x1400a938d  mov     rbp, rcx
0x1400a9390  lea     rcx, [r11-28h]
0x1400a9394  mov     rax, rdx
0x1400a9397  xor     ebx, ebx
0x1400a9399  mov     edx, 82h; DesiredAccess
0x1400a939e  mov     [r11-40h], rbx
0x1400a93a2  mov     r8, [r8]; ObjectType
0x1400a93a5  mov     [r11-48h], rcx
0x1400a93a9  mov     rcx, rax; Handle
0x1400a93ac  mov     [r11-28h], rbx
0x1400a93b0  call    cs:__imp_ObReferenceObjectByHandle
0x1400a93b7  nop     dword ptr [rax+rax+00h]
0x1400a93bc  mov     rsi, [rsp+68h+FileObject]
0x1400a93c1  mov     edi, eax
0x1400a93c3  test    eax, eax
0x1400a93c5  jns     short loc_1400A93E8
0x1400a93c7  mov     r9d, eax
0x1400a93ca  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400a93d1  mov     r8d, 394h
0x1400a93d7  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400a93de  call    VidTraceErrorStatusInternal0
0x1400a93e3  jmp     loc_1400A9546
0x1400a93e8  mov     rcx, rsi; FileObject
0x1400a93eb  call    cs:__imp_IoGetRelatedDeviceObject
0x1400a93f2  nop     dword ptr [rax+rax+00h]
0x1400a93f7  mov     r14, rax
0x1400a93fa  test    rax, rax
0x1400a93fd  jnz     short loc_1400A9425
0x1400a93ff  mov     edi, 0C000000Dh
0x1400a9404  mov     r9d, edi
0x1400a9407  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400a940e  mov     r8d, 3A0h
0x1400a9414  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400a941b  call    VidTraceErrorStatusInternal0
0x1400a9420  jmp     loc_1400A9546
0x1400a9425  lea     rax, [rsp+68h+arg_18]
0x1400a942d  xor     r9d, r9d; DesiredAccess
0x1400a9430  mov     [rsp+68h+Handle], rax; Handle
0x1400a9435  xor     r8d, r8d; PassedAccessState
0x1400a9438  mov     rax, cs:__imp_IoFileObjectType
0x1400a943f  mov     edx, 200h; HandleAttributes
0x1400a9444  mov     [rsp+68h+AccessMode], bl; AccessMode
0x1400a9448  mov     rcx, [rax]
0x1400a944b  mov     [rsp+68h+ObjectType], rcx; ObjectType
0x1400a9450  mov     rcx, rsi; Object
0x1400a9453  call    cs:__imp_ObOpenObjectByPointer
0x1400a945a  nop     dword ptr [rax+rax+00h]
0x1400a945f  mov     edi, eax
0x1400a9461  test    eax, eax
0x1400a9463  jns     short loc_1400A9486
0x1400a9465  mov     r9d, eax
0x1400a9468  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400a946f  mov     r8d, 3B7h
0x1400a9475  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400a947c  call    VidTraceErrorStatusInternal0
0x1400a9481  jmp     loc_1400A9546
0x1400a9486  mov     edx, 1
0x1400a948b  mov     rcx, rbp; P
0x1400a948e  call    VsmmMemXferpConnectionAlloc
0x1400a9493  mov     rbx, rax
0x1400a9496  test    rax, rax
0x1400a9499  jnz     short loc_1400A94C1
0x1400a949b  mov     edi, 0C000009Ah
0x1400a94a0  mov     r9d, edi
0x1400a94a3  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400a94aa  mov     r8d, 3C5h
0x1400a94b0  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400a94b7  call    VidTraceErrorStatusInternal0
0x1400a94bc  jmp     loc_1400A9546
0x1400a94c1  mov     dword ptr [rax+74h], 1
0x1400a94c8  mov     dword ptr [rax+70h], 2
0x1400a94cf  mov     rax, [rsp+68h+arg_18]
0x1400a94d7  mov     [rbx+88h], r14
0x1400a94de  lea     r14, [rbp+21A0h]
0x1400a94e5  mov     rcx, r14
0x1400a94e8  mov     [rbx+78h], rax
0x1400a94ec  mov     [rbx+80h], rsi
0x1400a94f3  call    VidAutoExpandPushLockAcquireExclusive
0x1400a94f8  cmp     qword ptr [rbp+21B0h], 0
0x1400a9500  jz      short loc_1400A9525
0x1400a9502  mov     edi, 0C0000184h
0x1400a9507  mov     r9d, edi
0x1400a950a  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400a9511  mov     r8d, 3D8h
0x1400a9517  lea     rcx, aVsmmmemxferioc; "VsmmMemXferIoctlConnectSrcOpen"
0x1400a951e  call    VidTraceErrorStatusInternal0
0x1400a9523  jmp     short loc_1400A953E
0x1400a9525  mov     [rbp+21B0h], rbx
0x1400a952c  xor     esi, esi
0x1400a952e  xor     ebx, ebx
0x1400a9530  mov     [rsp+68h+arg_18], 0FFFFFFFFFFFFFFFFh
0x1400a953c  xor     edi, edi
0x1400a953e  mov     rcx, r14
0x1400a9541  call    VidAutoExpandPushLockReleaseExclusive
0x1400a9546  mov     rcx, [rsp+68h+arg_18]; Handle
0x1400a954e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400a9552  jz      short loc_1400A9560
0x1400a9554  call    cs:__imp_ZwClose
0x1400a955b  nop     dword ptr [rax+rax+00h]
0x1400a9560  test    rsi, rsi
0x1400a9563  jz      short loc_1400A9574
0x1400a9565  mov     rcx, rsi; Object
0x1400a9568  call    cs:__imp_ObfDereferenceObject
0x1400a956f  nop     dword ptr [rax+rax+00h]
0x1400a9574  test    rbx, rbx
0x1400a9577  jz      short loc_1400A958C
0x1400a9579  lea     rcx, [rbx+10h]
0x1400a957d  mov     dl, 1
0x1400a957f  call    VidOpCtrlBlock
0x1400a9584  mov     rcx, rbx; P
0x1400a9587  call    VsmmMemXferpConnectionFreeInternal
0x1400a958c  mov     rbx, [rsp+68h+arg_0]
0x1400a9591  mov     eax, edi
0x1400a9593  mov     rbp, [rsp+68h+arg_8]
0x1400a9598  add     rsp, 50h
0x1400a959c  pop     r14
0x1400a959e  pop     rdi
0x1400a959f  pop     rsi
0x1400a95a0  retn
```
