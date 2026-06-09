# SpControlPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140033640`
- end: `0x1400338e5`
- name: `?SpControlPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `677`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x14001f2a0`
- `0x1400268c0`
- `0x140031e28`
- `0x140033640`
- `0x1400a1d08`
- `0x1400a3e78`
- `0x1400a6f58`
- `0x1400a7460`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140033774`
- `ntoskrnl!ObfReferenceObject` at `0x140033774`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400336d4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400336d4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033729`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033797`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033729`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033797`
- `ntoskrnl!IoDeleteDevice` at `0x140033858`
- `ntoskrnl!IoDeleteDevice` at `0x140033858`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400337b6`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400337dc`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140033870`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400337b6`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400337dc`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140033870`
- `ntoskrnl!IofCompleteRequest` at `0x1400338ae`
- `ntoskrnl!IofCompleteRequest` at `0x1400338ae`

## pseudocode

```c
__int64 __fastcall SpControlPnp(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  SP_CONTROL *v4; // rbp
  PIRP v5; // rbx
  unsigned int MinorFunction; // r8d
  struct _DEVICE_OBJECT *v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  char *v12; // r12
  int v13; // edx
  __int64 *v14; // rbp
  __int64 *i; // rcx
  _DWORD *v16; // r15
  int Status; // edi
  __int64 *v18; // rdi
  __int64 v19; // r14
  char v20; // al
  void *v21; // rcx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  int RootId; // eax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = (SP_CONTROL *)((char *)a1->DeviceExtension + 8);
  v5 = Irp;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1->DeviceExtension + 3);
  if ( MinorFunction <= 9 )
  {
    if ( MinorFunction == 9 )
    {
      IoForwardIrpSynchronously(v7, Irp);
      *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 4) |= 0xC0u;
      Status = v5->IoStatus.Status;
    }
    else
    {
      if ( CurrentStackLocation->MinorFunction )
      {
        v8 = MinorFunction - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 3;
              if ( v11 )
              {
                if ( v11 != 1 || CurrentStackLocation->Parameters.Read.Length )
                  return SpControlSkip(a1, Irp);
                v12 = (char *)v4 + 320;
                ExAcquirePushLockExclusiveEx((char *)v4 + 320, 0);
                v13 = 0;
                v14 = (__int64 *)((char *)v4 + 304);
                for ( i = (__int64 *)*v14; i != v14; i = (__int64 *)*i )
                {
                  if ( (unsigned __int8)(*((_BYTE *)i + 160) - 1) <= 2u )
                    ++v13;
                }
                v16 = SC_ENV::Allocate((unsigned int)(8 * v13 + 8), 0x58587053u, 0, 0);
                if ( !v16 )
                {
                  ExReleasePushLockExclusiveEx(v12, 0);
                  Status = -1073741670;
                  v5->IoStatus.Information = 0;
                  goto LABEL_43;
                }
                v18 = (__int64 *)*v14;
                v19 = 0;
                while ( v18 != v14 )
                {
                  v20 = *((_BYTE *)v18 + 160);
                  if ( v20 == 4 )
                  {
                    *((_BYTE *)v18 + 160) = 5;
                  }
                  else if ( (unsigned __int8)(v20 - 2) <= 1u )
                  {
                    v21 = (void *)v18[19];
                    *(_QWORD *)&v16[2 * v19 + 2] = v21;
                    v19 = (unsigned int)(v19 + 1);
                    ObfReferenceObject(v21);
                    *((_BYTE *)v18 + 160) = 3;
                  }
                  v18 = (__int64 *)*v18;
                }
                *v16 = v19;
                ExReleasePushLockExclusiveEx(v12, 0);
                v5->IoStatus.Information = (ULONG_PTR)v16;
                goto LABEL_25;
              }
            }
LABEL_47:
            Irp->IoStatus.Status = 0;
            return SpControlSkip(a1, Irp);
          }
LABEL_36:
          SP_CONTROL::Remove(v4);
          if ( CurrentStackLocation->MinorFunction == 2 )
          {
            SP_CONTROL::~SP_CONTROL(v4);
            WPP_MAIN_CB.DeviceExtension = 0;
            SP_QOS_CONTEXT::UnInitializeLimiterInternal();
            IoDeleteDevice(a1);
          }
LABEL_25:
          v5->IoStatus.Status = 0;
          goto LABEL_26;
        }
        goto LABEL_38;
      }
      IoForwardIrpSynchronously(v7, Irp);
      Status = v5->IoStatus.Status;
      if ( Status >= 0 )
        Status = SP_CONTROL::Start(v4);
    }
    goto LABEL_42;
  }
  v22 = MinorFunction - 10;
  if ( !v22 )
    goto LABEL_47;
  v23 = v22 - 1;
  if ( !v23 )
    goto LABEL_47;
  v24 = v23 - 8;
  if ( v24 )
  {
    v25 = v24 - 1;
    if ( !v25 )
    {
      IoForwardIrpSynchronously(v7, Irp);
      Status = 0;
      v5->IoStatus.Information = 32;
      goto LABEL_43;
    }
    v26 = v25 - 2;
    if ( v26 )
    {
      if ( v26 != 1 )
        return SpControlSkip(a1, Irp);
      goto LABEL_36;
    }
LABEL_38:
    Status = -1073741808;
    goto LABEL_43;
  }
  RootId = SpQueryRootId((struct SP_CONTROL *)v7, Irp);
  Status = RootId;
  if ( RootId >= 0 )
  {
    v5->IoStatus.Status = RootId;
    goto LABEL_26;
  }
  if ( RootId != -1073741637 )
  {
LABEL_42:
    if ( Status == -1073741637 )
    {
      Status = v5->IoStatus.Status;
      goto LABEL_45;
    }
LABEL_43:
    v5->IoStatus.Status = Status;
LABEL_45:
    IofCompleteRequest(v5, 0);
    return (unsigned int)Status;
  }
LABEL_26:
  Irp = v5;
  return SpControlSkip(a1, Irp);
}

```

## disassembly

```asm
0x140033640  push    rbx
0x140033642  push    rbp
0x140033643  push    rsi
0x140033644  push    rdi
0x140033645  push    r12
0x140033647  push    r14
0x140033649  push    r15
0x14003364b  sub     rsp, 20h
0x14003364f  mov     rbp, [rcx+40h]
0x140033653  mov     rsi, rcx
0x140033656  mov     rdi, [rdx+0B8h]
0x14003365d  add     rbp, 8
0x140033661  mov     rbx, rdx
0x140033664  mov     r14d, 0C00000BBh
0x14003366a  movzx   r8d, byte ptr [rdi+1]
0x14003366f  mov     rcx, [rbp+10h]; struct SP_CONTROL *
0x140033673  cmp     r8d, 9
0x140033677  ja      loc_1400337FB
0x14003367d  jz      loc_1400337DC
0x140033683  test    r8d, r8d
0x140033686  jz      loc_1400337B6
0x14003368c  sub     r8d, 1
0x140033690  jz      loc_140033869
0x140033696  sub     r8d, 1
0x14003369a  jz      loc_14003382B
0x1400336a0  sub     r8d, 1
0x1400336a4  jz      loc_1400338C6
0x1400336aa  sub     r8d, 3
0x1400336ae  jz      loc_1400338C6
0x1400336b4  cmp     r8d, 1
0x1400336b8  jnz     loc_1400338CD
0x1400336be  cmp     dword ptr [rdi+8], 0
0x1400336c2  jnz     loc_1400338CD
0x1400336c8  lea     r12, [rbp+140h]
0x1400336cf  xor     edx, edx
0x1400336d1  mov     rcx, r12
0x1400336d4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400336db  nop     dword ptr [rax+rax+00h]
0x1400336e0  xor     edx, edx
0x1400336e2  add     rbp, 130h
0x1400336e9  mov     rcx, [rbp+0]
0x1400336ed  jmp     short loc_140033700
0x1400336ef  mov     al, [rcx+0A0h]
0x1400336f5  dec     al
0x1400336f7  cmp     al, 2
0x1400336f9  ja      short loc_1400336FD
0x1400336fb  inc     edx
0x1400336fd  mov     rcx, [rcx]
0x140033700  cmp     rcx, rbp
0x140033703  jnz     short loc_1400336EF
0x140033705  lea     ecx, ds:8[rdx*8]; unsigned __int64
0x14003370c  xor     r9d, r9d; unsigned int
0x14003370f  mov     edx, 58587053h; unsigned int
0x140033714  xor     r8d, r8d; unsigned __int8
0x140033717  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003371c  mov     r15, rax
0x14003371f  test    rax, rax
0x140033722  jnz     short loc_140033743
0x140033724  xor     edx, edx
0x140033726  mov     rcx, r12
0x140033729  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140033730  nop     dword ptr [rax+rax+00h]
0x140033735  mov     edi, 0C000009Ah
0x14003373a  mov     [rbx+38h], r15
0x14003373e  jmp     loc_1400338A1
0x140033743  mov     rdi, [rbp+0]
0x140033747  xor     r14d, r14d
0x14003374a  jmp     short loc_14003378A
0x14003374c  mov     al, [rdi+0A0h]
0x140033752  cmp     al, 4
0x140033754  jnz     short loc_14003375F
0x140033756  mov     byte ptr [rdi+0A0h], 5
0x14003375d  jmp     short loc_140033787
0x14003375f  sub     al, 2
0x140033761  cmp     al, 1
0x140033763  ja      short loc_140033787
0x140033765  mov     rcx, [rdi+98h]; Object
0x14003376c  mov     [r15+r14*8+8], rcx
0x140033771  inc     r14d
0x140033774  call    cs:__imp_ObfReferenceObject
0x14003377b  nop     dword ptr [rax+rax+00h]
0x140033780  mov     byte ptr [rdi+0A0h], 3
0x140033787  mov     rdi, [rdi]
0x14003378a  cmp     rdi, rbp
0x14003378d  jnz     short loc_14003374C
0x14003378f  xor     edx, edx
0x140033791  mov     [r15], r14d
0x140033794  mov     rcx, r12
0x140033797  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14003379e  nop     dword ptr [rax+rax+00h]
0x1400337a3  mov     [rbx+38h], r15
0x1400337a7  mov     dword ptr [rbx+30h], 0
0x1400337ae  mov     rdx, rbx; Irp
0x1400337b1  jmp     loc_1400338CD
0x1400337b6  call    cs:__imp_IoForwardIrpSynchronously
0x1400337bd  nop     dword ptr [rax+rax+00h]
0x1400337c2  mov     edi, [rbx+30h]
0x1400337c5  test    edi, edi
0x1400337c7  js      loc_14003389C
0x1400337cd  mov     rcx, rbp; this
0x1400337d0  call    ?Start@SP_CONTROL@@QEAAJXZ; SP_CONTROL::Start(void)
0x1400337d5  mov     edi, eax
0x1400337d7  jmp     loc_14003389C
0x1400337dc  call    cs:__imp_IoForwardIrpSynchronously
0x1400337e3  nop     dword ptr [rax+rax+00h]
0x1400337e8  mov     rax, [rdi+8]
0x1400337ec  or      dword ptr [rax+4], 0C0h
0x1400337f3  mov     edi, [rbx+30h]
0x1400337f6  jmp     loc_14003389C
0x1400337fb  sub     r8d, 0Ah
0x1400337ff  jz      loc_1400338C6
0x140033805  sub     r8d, 1
0x140033809  jz      loc_1400338C6
0x14003380f  sub     r8d, 8
0x140033813  jz      short loc_140033888
0x140033815  sub     r8d, 1
0x140033819  jz      short loc_140033870
0x14003381b  sub     r8d, 2
0x14003381f  jz      short loc_140033869
0x140033821  cmp     r8d, 1
0x140033825  jnz     loc_1400338CD
0x14003382b  mov     rcx, rbp; this
0x14003382e  call    ?Remove@SP_CONTROL@@QEAAXXZ; SP_CONTROL::Remove(void)
0x140033833  cmp     byte ptr [rdi+1], 2
0x140033837  jnz     loc_1400337A7
0x14003383d  mov     rcx, rbp; this
0x140033840  call    ??1SP_CONTROL@@QEAA@XZ; SP_CONTROL::~SP_CONTROL(void)
0x140033845  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x140033850  call    ?UnInitializeLimiterInternal@SP_QOS_CONTEXT@@SAXXZ; SP_QOS_CONTEXT::UnInitializeLimiterInternal(void)
0x140033855  mov     rcx, rsi; DeviceObject
0x140033858  call    cs:__imp_IoDeleteDevice
0x14003385f  nop     dword ptr [rax+rax+00h]
0x140033864  jmp     loc_1400337A7
0x140033869  mov     edi, 0C0000010h
0x14003386e  jmp     short loc_1400338A1
0x140033870  call    cs:__imp_IoForwardIrpSynchronously
0x140033877  nop     dword ptr [rax+rax+00h]
0x14003387c  xor     edi, edi
0x14003387e  mov     qword ptr [rbx+38h], 20h ; ' '
0x140033886  jmp     short loc_1400338A1
0x140033888  call    ?SpQueryRootId@@YAJPEAVSP_CONTROL@@PEAU_IRP@@@Z; SpQueryRootId(SP_CONTROL *,_IRP *)
0x14003388d  mov     edi, eax
0x14003388f  test    eax, eax
0x140033891  jns     short loc_1400338BE
0x140033893  cmp     eax, r14d
0x140033896  jz      loc_1400337AE
0x14003389c  cmp     edi, r14d
0x14003389f  jz      short loc_1400338A6
0x1400338a1  mov     [rbx+30h], edi
0x1400338a4  jmp     short loc_1400338A9
0x1400338a6  mov     edi, [rbx+30h]
0x1400338a9  xor     edx, edx; PriorityBoost
0x1400338ab  mov     rcx, rbx; Irp
0x1400338ae  call    cs:__imp_IofCompleteRequest
0x1400338b5  nop     dword ptr [rax+rax+00h]
0x1400338ba  mov     eax, edi
0x1400338bc  jmp     short loc_1400338D5
0x1400338be  mov     [rbx+30h], eax
0x1400338c1  jmp     loc_1400337AE
0x1400338c6  mov     dword ptr [rdx+30h], 0
0x1400338cd  mov     rcx, rsi; struct _DEVICE_OBJECT *
0x1400338d0  call    ?SpControlSkip@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpControlSkip(_DEVICE_OBJECT *,_IRP *)
0x1400338d5  add     rsp, 20h
0x1400338d9  pop     r15
0x1400338db  pop     r14
0x1400338dd  pop     r12
0x1400338df  pop     rdi
0x1400338e0  pop     rsi
0x1400338e1  pop     rbp
0x1400338e2  pop     rbx
0x1400338e3  retn
```
