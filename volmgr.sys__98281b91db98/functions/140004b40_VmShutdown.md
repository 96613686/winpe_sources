# VmShutdown

- ea: `0x140004b40`
- end: `0x140004df9`
- name: `VmShutdown`
- size: `697`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400014d0`
- `0x1400029e0`
- `0x140002a30`
- `0x140004b40`
- `0x140005090`
- `0x140016a20`
- `0x140016fc0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140004ddb`
- `ntoskrnl!IofCallDriver` at `0x140004ddb`
- `ntoskrnl!IofCompleteRequest` at `0x140004d02`
- `ntoskrnl!IofCompleteRequest` at `0x140004d02`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004c20`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004c79`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004c20`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004c79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004c91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004c91`
- `ntoskrnl!ExAllocatePool2` at `0x140004bb3`
- `ntoskrnl!ExAllocatePool2` at `0x140004bb3`

## pseudocode

```c
NTSTATUS __fastcall VmShutdown(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi
  _QWORD **v4; // r14
  unsigned int v5; // ecx
  _QWORD *v6; // rax
  _QWORD *Pool2; // r13
  int v8; // ebx
  unsigned int v9; // r12d
  _QWORD *i; // r15
  _QWORD *v11; // rbp
  int v12; // ebx
  __int64 v13; // rax
  unsigned int j; // ebp
  __int64 v15; // rbx
  int v16; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v19; // rax
  int v20; // [rsp+20h] [rbp-58h]

  v2 = *(_QWORD *)(a1 + 64);
  if ( !*(_DWORD *)(v2 + 16) )
  {
    VmpAcquireAll((struct VM_ROOT_EXTENSION *)v2);
    if ( *(_QWORD *)(v2 + 392) )
    {
      v4 = (_QWORD **)(v2 + 208);
      v5 = 0;
      v6 = *(_QWORD **)(v2 + 208);
      if ( v6 == (_QWORD *)(v2 + 208) )
        goto LABEL_18;
      do
      {
        v6 = (_QWORD *)*v6;
        ++v5;
      }
      while ( v6 != v4 );
      if ( !v5 )
      {
LABEL_18:
        VmpReleaseAll((struct VM_ROOT_EXTENSION *)v2);
      }
      else
      {
        Pool2 = (_QWORD *)ExAllocatePool2(66, 8LL * v5, 538987862);
        if ( !Pool2 )
        {
          VmpReleaseAll((struct VM_ROOT_EXTENSION *)v2);
          v8 = -1073741670;
          a2->IoStatus.Status = -1073741670;
LABEL_25:
          a2->IoStatus.Information = 0;
          IofCompleteRequest(a2, 0);
          return v8;
        }
        v9 = 0;
        for ( i = *v4; i != v4; i = (_QWORD *)*i )
        {
          v11 = i - 4;
          VmpAcquireRundown((struct VM_VOLUME_EXTENSION *)(i - 4));
          v12 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)(i - 4), 0, 1u, 1u, 1);
          VmpReleaseRundown((struct VM_VOLUME_EXTENSION *)(i - 4));
          if ( v12 >= 0 )
          {
            if ( *((_BYTE *)v11 + 426) )
            {
              v13 = v9++;
              Pool2[v13] = v11;
            }
            else
            {
              ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[14]);
            }
          }
        }
        VmpReleaseAll((struct VM_ROOT_EXTENSION *)v2);
        for ( j = 0; j < v9; ++j )
        {
          v15 = Pool2[j];
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(v2 + 392) + 224LL))(*(_QWORD *)(v15 + 432));
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v15 + 112));
        }
        ExFreePoolWithTag(Pool2, 0);
      }
      VmpAcquireAll((struct VM_ROOT_EXTENSION *)v2);
      (*(void (**)(void))(*(_QWORD *)(v2 + 392) + 80LL))();
    }
    VmpReleaseAll((struct VM_ROOT_EXTENSION *)v2);
    v8 = 0;
    a2->IoStatus.Status = 0;
    goto LABEL_25;
  }
  v16 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 1);
  v8 = v16;
  if ( v16 == 259 )
    return 259;
  if ( v16 < 0 )
  {
    a2->IoStatus.Status = v16;
    goto LABEL_25;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v19 = a2->Tail.Overlay.CurrentStackLocation;
  v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpRefCountCompletionRoutine;
  v19[-1].Context = (PVOID)16;
  v19[-1].Control = -32;
  if ( *(_BYTE *)(v2 + 426) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(*(_QWORD *)(v2 + 8) + 392LL) + 224LL))(*(_QWORD *)(v2 + 432));
    --a2->Tail.Overlay.CurrentStackLocation;
    --a2->CurrentLocation;
    LOBYTE(v20) = 0;
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    (*(void (__fastcall **)(_QWORD, IRP *, void (__fastcall *)(void *, int), IRP *, int))(*(_QWORD *)(*(_QWORD *)(v2 + 8) + 392LL)
                                                                                        + 216LL))(
      *(_QWORD *)(v2 + 432),
      a2,
      VmBroadcastIrpCompletionRoutine,
      a2,
      v20);
    return 259;
  }
  return IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 368), a2);
}

```

## disassembly

```asm
0x140004b40  push    rbx
0x140004b42  push    rbp
0x140004b43  push    rsi
0x140004b44  push    rdi
0x140004b45  push    r12
0x140004b47  push    r13
0x140004b49  push    r14
0x140004b4b  push    r15
0x140004b4d  sub     rsp, 38h
0x140004b51  mov     rdi, [rcx+40h]
0x140004b55  xor     r15d, r15d
0x140004b58  mov     rsi, rdx
0x140004b5b  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140004b5e  cmp     [rdi+10h], r15d
0x140004b62  jnz     loc_140004CD0
0x140004b68  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x140004b6d  cmp     [rdi+188h], r15
0x140004b74  jz      loc_140004CBF
0x140004b7a  lea     r14, [rdi+0D0h]
0x140004b81  mov     ecx, r15d
0x140004b84  mov     rax, [r14]
0x140004b87  cmp     rax, r14
0x140004b8a  jz      loc_140004C9F
0x140004b90  mov     rax, [rax]
0x140004b93  inc     ecx
0x140004b95  cmp     rax, r14
0x140004b98  jnz     short loc_140004B90
0x140004b9a  test    ecx, ecx
0x140004b9c  jz      loc_140004C9F
0x140004ba2  mov     edx, ecx
0x140004ba4  mov     r8d, 20204D56h
0x140004baa  shl     rdx, 3
0x140004bae  mov     ecx, 42h ; 'B'
0x140004bb3  call    cs:__imp_ExAllocatePool2
0x140004bba  nop     dword ptr [rax+rax+00h]
0x140004bbf  mov     r13, rax
0x140004bc2  test    rax, rax
0x140004bc5  jnz     short loc_140004BDC
0x140004bc7  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140004bca  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140004bcf  mov     ebx, 0C000009Ah
0x140004bd4  mov     [rsi+30h], ebx
0x140004bd7  jmp     loc_140004CF9
0x140004bdc  mov     r12d, r15d
0x140004bdf  mov     r15, [r14]
0x140004be2  jmp     short loc_140004C3C
0x140004be4  lea     rbp, [r15-20h]
0x140004be8  mov     rcx, rbp; struct VM_VOLUME_EXTENSION *
0x140004beb  call    ?VmpAcquireRundown@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpAcquireRundown(VM_VOLUME_EXTENSION *)
0x140004bf0  mov     r9b, 1; unsigned __int8
0x140004bf3  mov     byte ptr [rsp+78h+var_58], 1; char
0x140004bf8  mov     r8b, r9b; unsigned __int8
0x140004bfb  xor     edx, edx; struct _IRP *
0x140004bfd  mov     rcx, rbp; struct VM_VOLUME_EXTENSION *
0x140004c00  call    ?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z; VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)
0x140004c05  mov     rcx, rbp; struct VM_VOLUME_EXTENSION *
0x140004c08  mov     ebx, eax
0x140004c0a  call    ?VmpReleaseRundown@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundown(VM_VOLUME_EXTENSION *)
0x140004c0f  test    ebx, ebx
0x140004c11  js      short loc_140004C39
0x140004c13  cmp     byte ptr [rbp+1AAh], 0
0x140004c1a  jnz     short loc_140004C2E
0x140004c1c  mov     rcx, [rbp+70h]; RunRefCacheAware
0x140004c20  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140004c27  nop     dword ptr [rax+rax+00h]
0x140004c2c  jmp     short loc_140004C39
0x140004c2e  mov     eax, r12d
0x140004c31  inc     r12d
0x140004c34  mov     [r13+rax*8+0], rbp
0x140004c39  mov     r15, [r15]
0x140004c3c  cmp     r15, r14
0x140004c3f  jnz     short loc_140004BE4
0x140004c41  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140004c44  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140004c49  xor     r15d, r15d
0x140004c4c  mov     ebp, r15d
0x140004c4f  test    r12d, r12d
0x140004c52  jz      short loc_140004C8C
0x140004c54  mov     eax, ebp
0x140004c56  mov     rbx, [r13+rax*8+0]
0x140004c5b  mov     rax, [rdi+188h]
0x140004c62  mov     rcx, [rbx+1B0h]
0x140004c69  mov     rax, [rax+0E0h]
0x140004c70  call    _guard_dispatch_icall
0x140004c75  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140004c79  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140004c80  nop     dword ptr [rax+rax+00h]
0x140004c85  inc     ebp
0x140004c87  cmp     ebp, r12d
0x140004c8a  jb      short loc_140004C54
0x140004c8c  xor     edx, edx; Tag
0x140004c8e  mov     rcx, r13; P
0x140004c91  call    cs:__imp_ExFreePoolWithTag
0x140004c98  nop     dword ptr [rax+rax+00h]
0x140004c9d  jmp     short loc_140004CA7
0x140004c9f  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140004ca2  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140004ca7  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140004caa  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x140004caf  mov     rax, [rdi+188h]
0x140004cb6  mov     rax, [rax+50h]
0x140004cba  call    _guard_dispatch_icall
0x140004cbf  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140004cc2  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140004cc7  mov     ebx, r15d
0x140004cca  mov     [rsi+30h], r15d
0x140004cce  jmp     short loc_140004CF9
0x140004cd0  mov     r9b, 1; unsigned __int8
0x140004cd3  mov     byte ptr [rsp+78h+var_58], 1; char
0x140004cd8  mov     r8b, r9b; unsigned __int8
0x140004cdb  call    ?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z; VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)
0x140004ce0  mov     ebp, 103h
0x140004ce5  mov     ebx, eax
0x140004ce7  cmp     eax, ebp
0x140004ce9  jnz     short loc_140004CF2
0x140004ceb  mov     eax, ebp
0x140004ced  jmp     loc_140004DE7
0x140004cf2  test    eax, eax
0x140004cf4  jns     short loc_140004D15
0x140004cf6  mov     [rsi+30h], eax
0x140004cf9  xor     edx, edx; PriorityBoost
0x140004cfb  mov     [rsi+38h], r15
0x140004cff  mov     rcx, rsi; Irp
0x140004d02  call    cs:__imp_IofCompleteRequest
0x140004d09  nop     dword ptr [rax+rax+00h]
0x140004d0e  mov     eax, ebx
0x140004d10  jmp     loc_140004DE7
0x140004d15  mov     rax, [rsi+0B8h]
0x140004d1c  lea     rcx, VmpRefCountCompletionRoutine
0x140004d23  movups  xmm0, xmmword ptr [rax]
0x140004d26  movups  xmmword ptr [rax-48h], xmm0
0x140004d2a  movups  xmm1, xmmword ptr [rax+10h]
0x140004d2e  movups  xmmword ptr [rax-38h], xmm1
0x140004d32  movups  xmm0, xmmword ptr [rax+20h]
0x140004d36  movups  xmmword ptr [rax-28h], xmm0
0x140004d3a  movsd   xmm1, qword ptr [rax+30h]
0x140004d3f  movsd   qword ptr [rax-18h], xmm1
0x140004d44  mov     [rax-45h], r15b
0x140004d48  mov     rax, [rsi+0B8h]
0x140004d4f  mov     [rax-10h], rcx
0x140004d53  mov     qword ptr [rax-8], 10h
0x140004d5b  mov     byte ptr [rax-45h], 0E0h
0x140004d5f  cmp     [rdi+1AAh], r15b
0x140004d66  jz      short loc_140004DD1
0x140004d68  mov     rax, [rdi+8]
0x140004d6c  mov     rcx, [rax+188h]
0x140004d73  mov     rax, [rcx+0E0h]
0x140004d7a  mov     rcx, [rdi+1B0h]
0x140004d81  call    _guard_dispatch_icall
0x140004d86  add     qword ptr [rsi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140004d8e  lea     r8, ?VmBroadcastIrpCompletionRoutine@@YAXPEAXJ@Z; VmBroadcastIrpCompletionRoutine(void *,long)
0x140004d95  dec     byte ptr [rsi+43h]
0x140004d98  mov     r9, rsi
0x140004d9b  mov     rax, [rsi+0B8h]
0x140004da2  mov     rdx, rsi
0x140004da5  mov     byte ptr [rsp+78h+var_58], r15b
0x140004daa  or      byte ptr [rax+3], 1
0x140004dae  mov     rax, [rdi+8]
0x140004db2  mov     rcx, [rax+188h]
0x140004db9  mov     rax, [rcx+0D8h]
0x140004dc0  mov     rcx, [rdi+1B0h]
0x140004dc7  call    _guard_dispatch_icall
0x140004dcc  jmp     loc_140004CEB
0x140004dd1  mov     rcx, [rdi+170h]; DeviceObject
0x140004dd8  mov     rdx, rsi; Irp
0x140004ddb  call    cs:__imp_IofCallDriver
0x140004de2  nop     dword ptr [rax+rax+00h]
0x140004de7  add     rsp, 38h
0x140004deb  pop     r15
0x140004ded  pop     r14
0x140004def  pop     r13
0x140004df1  pop     r12
0x140004df3  pop     rdi
0x140004df4  pop     rsi
0x140004df5  pop     rbp
0x140004df6  pop     rbx
0x140004df7  retn
```
