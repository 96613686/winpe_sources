# VmpNotify(VM_VOLUME_EXTENSION *,_GUID const *,ushort,void *)

- ea: `0x14000f6fc`
- end: `0x14000f819`
- name: `?VmpNotify@@YAXPEAVVM_VOLUME_EXTENSION@@PEBU_GUID@@GPEAX@Z`
- size: `285`
- prototype: `void(struct VM_VOLUME_EXTENSION *, const struct _GUID *, unsigned __int16, void *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000e888`
- `0x14000eba0`
- `0x14000f3b0`
- `0x140010ad8`
- `0x140015da0`

## callees

- `0x140005050`
- `0x140005240`
- `0x14000f6fc`

## import_xrefs

- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14000f7d1`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14000f7d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7e7`
- `ntoskrnl!ExAllocatePool2` at `0x14000f77b`
- `ntoskrnl!ExAllocatePool2` at `0x14000f77b`

## pseudocode

```c
void __fastcall VmpNotify(struct VM_VOLUME_EXTENSION *a1, const struct _GUID *a2, unsigned __int16 a3, void *a4)
{
  size_t v4; // rdi
  char v5; // al
  _OWORD *Pool2; // rbx
  char v10; // si
  __int16 v11; // cx
  __int128 v12; // xmm0
  _OWORD NotificationStructure[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v14; // [rsp+40h] [rbp-48h]

  v4 = a3;
  v14 = 0;
  v5 = *((_BYTE *)a1 + 156);
  memset(NotificationStructure, 0, sizeof(NotificationStructure));
  if ( v5 )
  {
    Pool2 = NotificationStructure;
    v10 = 0;
    v11 = 36;
    if ( a3 )
    {
      Pool2 = (_OWORD *)ExAllocatePool2(66, (unsigned __int16)(a3 + 36), 538987862);
      if ( !Pool2 )
        return;
      v11 = v4 + 36;
      v10 = 1;
    }
    *(_WORD *)Pool2 = 1;
    *((_WORD *)Pool2 + 1) = v11;
    v12 = (__int128)*a2;
    *((_QWORD *)Pool2 + 3) = 0;
    *((_DWORD *)Pool2 + 8) = -1;
    *(_OWORD *)((char *)Pool2 + 4) = v12;
    if ( (_WORD)v4 )
      memmove((char *)Pool2 + 36, a4, v4);
    IoReportTargetDeviceChangeAsynchronous(*(PDEVICE_OBJECT *)a1, Pool2, 0, 0);
    if ( v10 )
      ExFreePoolWithTag(Pool2, 0);
  }
}

```

## disassembly

```asm
0x14000f6fc  mov     [rsp+arg_8], rbx
0x14000f701  push    rbp
0x14000f702  push    rsi
0x14000f703  push    rdi
0x14000f704  push    r12
0x14000f706  push    r13
0x14000f708  push    r14
0x14000f70a  push    r15
0x14000f70c  sub     rsp, 50h
0x14000f710  mov     rax, cs:__security_cookie
0x14000f717  xor     rax, rsp
0x14000f71a  mov     [rsp+88h+var_40], rax
0x14000f71f  xor     eax, eax
0x14000f721  movzx   edi, r8w
0x14000f725  xorps   xmm0, xmm0
0x14000f728  mov     [rsp+88h+var_48], rax
0x14000f72d  mov     al, [rcx+9Ch]
0x14000f733  xor     r12d, r12d
0x14000f736  mov     rbp, r9
0x14000f739  mov     r15, rdx
0x14000f73c  mov     r14, rcx
0x14000f73f  movups  [rsp+88h+NotificationStructure], xmm0
0x14000f744  movups  [rsp+88h+var_58], xmm0
0x14000f749  test    al, al
0x14000f74b  jz      loc_14000F7F3
0x14000f751  lea     rbx, [rsp+88h+NotificationStructure]
0x14000f756  mov     sil, r12b
0x14000f759  lea     ecx, [r12+24h]
0x14000f75e  lea     r13d, [r12+1]
0x14000f763  test    di, di
0x14000f766  jz      short loc_14000F795
0x14000f768  lea     eax, [rcx+rdi]
0x14000f76b  mov     r8d, 20204D56h
0x14000f771  movzx   esi, ax
0x14000f774  lea     ecx, [r12+42h]
0x14000f779  mov     edx, esi
0x14000f77b  call    cs:__imp_ExAllocatePool2
0x14000f782  nop     dword ptr [rax+rax+00h]
0x14000f787  mov     rbx, rax
0x14000f78a  test    rax, rax
0x14000f78d  jz      short loc_14000F7F3
0x14000f78f  movzx   ecx, si
0x14000f792  mov     sil, r13b
0x14000f795  mov     [rbx], r13w
0x14000f799  mov     [rbx+2], cx
0x14000f79d  movups  xmm0, xmmword ptr [r15]
0x14000f7a1  mov     [rbx+18h], r12
0x14000f7a5  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x14000f7ac  movdqu  xmmword ptr [rbx+4], xmm0
0x14000f7b1  test    di, di
0x14000f7b4  jz      short loc_14000F7C5
0x14000f7b6  mov     r8, rdi; Size
0x14000f7b9  lea     rcx, [rbx+24h]; void *
0x14000f7bd  mov     rdx, rbp; Src
0x14000f7c0  call    memmove
0x14000f7c5  mov     rcx, [r14]; PhysicalDeviceObject
0x14000f7c8  xor     r9d, r9d; Context
0x14000f7cb  xor     r8d, r8d; Callback
0x14000f7ce  mov     rdx, rbx; NotificationStructure
0x14000f7d1  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x14000f7d8  nop     dword ptr [rax+rax+00h]
0x14000f7dd  test    sil, sil
0x14000f7e0  jz      short loc_14000F7F3
0x14000f7e2  xor     edx, edx; Tag
0x14000f7e4  mov     rcx, rbx; P
0x14000f7e7  call    cs:__imp_ExFreePoolWithTag
0x14000f7ee  nop     dword ptr [rax+rax+00h]
0x14000f7f3  mov     rcx, [rsp+88h+var_40]
0x14000f7f8  xor     rcx, rsp; StackCookie
0x14000f7fb  call    __security_check_cookie
0x14000f800  mov     rbx, [rsp+88h+arg_8]
0x14000f808  add     rsp, 50h
0x14000f80c  pop     r15
0x14000f80e  pop     r14
0x14000f810  pop     r13
0x14000f812  pop     r12
0x14000f814  pop     rdi
0x14000f815  pop     rsi
0x14000f816  pop     rbp
0x14000f817  retn
```
