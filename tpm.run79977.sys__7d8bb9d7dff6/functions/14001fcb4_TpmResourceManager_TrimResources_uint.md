# TpmResourceManager::TrimResources(uint)

- ea: `0x14001fcb4`
- end: `0x14001ff37`
- name: `?TrimResources@TpmResourceManager@@AEAAJI@Z`
- size: `643`
- prototype: `__int64 __fastcall(TpmResourceManager *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x140015db8`
- `0x14001f584`
- `0x14001f9fc`
- `0x14001fcb4`

## callees

- `0x140009278`
- `0x14001300c`
- `0x14001506c`
- `0x140016014`
- `0x14001a770`
- `0x14001f3a0`
- `0x14001f534`
- `0x14001f560`
- `0x14001fcb4`
- `0x14001ff40`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001fee0`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001fee0`

## pseudocode

```c
__int64 __fastcall TpmResourceManager::TrimResources(TpmResourceManager *this, unsigned int a2)
{
  TpmResourceManager *v2; // r15
  unsigned int v3; // ebx
  TpmResourceManager *v4; // rsi
  int v5; // edi
  TpmResource *v8; // rbp
  unsigned int Type; // r12d
  struct _LIST_ENTRY *v10; // rcx
  int i; // ebp
  TpmResourceManager *j; // rsi
  unsigned int v13; // eax
  struct _LIST_ENTRY *v14; // rcx
  unsigned int PhysicalHandle; // eax
  union _LARGE_INTEGER Interval; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+78h] [rbp+10h] BYREF

  v2 = (TpmResourceManager *)((char *)this + 8);
  v3 = 0;
  v4 = (TpmResourceManager *)*((_QWORD *)this + 1);
  v5 = 0;
  v18 = 0;
  if ( v4 == (TpmResourceManager *)((char *)this + 8) )
    goto LABEL_9;
  do
  {
    v8 = v4;
    v4 = *(TpmResourceManager **)v4;
    if ( !*((_BYTE *)v8 + 76) )
    {
      Type = TpmResource::GetType(v8);
      if ( (int)TpmResource::Flush(v10, this) >= 0 && Type == a2 )
        v18 = ++v3;
      TpmResourceManager::DeleteResource(this, v8, 0);
    }
  }
  while ( v4 != v2 );
  if ( !v3 )
  {
LABEL_9:
    TpmResourceManager::SyncResources(this, a2, &v18);
    v3 = v18;
  }
  for ( i = 0; i < (a2 != 5) + 1; ++i )
  {
    if ( v3 )
      goto LABEL_38;
    for ( j = *(TpmResourceManager **)v2; j != v2 && !v3; j = *(TpmResourceManager **)j )
    {
      v13 = TpmResource::GetType(j);
      if ( !*((_DWORD *)j + 18) )
      {
        if ( i )
        {
          if ( i != 1 || v13 != 5 )
          {
            while ( 1 )
            {
LABEL_21:
              v5 = TpmResource::Unload(j, this);
              if ( !i && TpmResource::GetType(j) == 2 && v5 == -1071054749 )
                v5 = TpmResource::Flush(v14, this);
              if ( v5 >= 0 )
                break;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                PhysicalHandle = TpmResource::GetPhysicalHandle(j);
                WPP_SF_Dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids,
                  PhysicalHandle);
              }
              if ( !TpmResourceManager::IsTpmLowResourceStatus(v5)
                || (int)TpmResourceManager::TrimResources(this, 5u) < 0 )
              {
                goto LABEL_33;
              }
            }
            v3 = 1;
          }
        }
        else if ( v13 == a2 )
        {
          goto LABEL_21;
        }
      }
LABEL_33:
      ;
    }
  }
  if ( !v3 )
  {
    v5 = -1071054831;
LABEL_45:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids,
        (unsigned int)v5);
    return (unsigned int)v5;
  }
LABEL_38:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids, v3);
  Interval.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids, 1);
  Interval.QuadPart = -10000;
  KeDelayExecutionThread(0, 0, &Interval);
  if ( v5 < 0 )
    goto LABEL_45;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001fcb4  mov     [rsp+arg_10], rbx
0x14001fcb9  push    rbp
0x14001fcba  push    rsi
0x14001fcbb  push    rdi
0x14001fcbc  push    r12
0x14001fcbe  push    r13
0x14001fcc0  push    r14
0x14001fcc2  push    r15
0x14001fcc4  sub     rsp, 30h
0x14001fcc8  lea     r15, [rcx+8]
0x14001fccc  xor     ebx, ebx
0x14001fcce  mov     rsi, [r15]
0x14001fcd1  xor     edi, edi
0x14001fcd3  mov     [rsp+68h+arg_8], ebx
0x14001fcd7  mov     r13d, edx
0x14001fcda  mov     r14, rcx
0x14001fcdd  cmp     rsi, r15
0x14001fce0  jz      short loc_14001FD27
0x14001fce2  mov     rbp, rsi
0x14001fce5  mov     rsi, [rsi]
0x14001fce8  cmp     [rbp+4Ch], dil
0x14001fcec  jnz     short loc_14001FD1E
0x14001fcee  mov     rcx, rbp; this
0x14001fcf1  call    ?GetType@TpmResource@@QEBAIXZ; TpmResource::GetType(void)
0x14001fcf6  mov     rdx, r14; struct TpmResourceManager *
0x14001fcf9  mov     r12d, eax
0x14001fcfc  call    ?Flush@TpmResource@@QEAAJPEAVTpmResourceManager@@@Z; TpmResource::Flush(TpmResourceManager *)
0x14001fd01  test    eax, eax
0x14001fd03  js      short loc_14001FD10
0x14001fd05  cmp     r12d, r13d
0x14001fd08  jnz     short loc_14001FD10
0x14001fd0a  inc     ebx
0x14001fd0c  mov     [rsp+68h+arg_8], ebx
0x14001fd10  xor     r8d, r8d; bool
0x14001fd13  mov     rdx, rbp; struct TpmResource *
0x14001fd16  mov     rcx, r14; this
0x14001fd19  call    ?DeleteResource@TpmResourceManager@@AEAAXPEAVTpmResource@@_N@Z; TpmResourceManager::DeleteResource(TpmResource *,bool)
0x14001fd1e  cmp     rsi, r15
0x14001fd21  jnz     short loc_14001FCE2
0x14001fd23  test    ebx, ebx
0x14001fd25  jnz     short loc_14001FD3B
0x14001fd27  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x14001fd2c  mov     edx, r13d; unsigned int
0x14001fd2f  mov     rcx, r14; this
0x14001fd32  call    ?SyncResources@TpmResourceManager@@QEAAJIPEAI@Z; TpmResourceManager::SyncResources(uint,uint *)
0x14001fd37  mov     ebx, [rsp+68h+arg_8]
0x14001fd3b  xor     r12d, r12d
0x14001fd3e  xor     ebp, ebp
0x14001fd40  cmp     r13d, 5
0x14001fd44  setnz   r12b
0x14001fd48  inc     r12d
0x14001fd4b  mov     sil, 4
0x14001fd4e  cmp     ebp, r12d
0x14001fd51  jge     loc_14001FE50
0x14001fd57  test    ebx, ebx
0x14001fd59  jnz     loc_14001FE65
0x14001fd5f  mov     rsi, [r15]
0x14001fd62  jmp     loc_14001FE40
0x14001fd67  test    ebx, ebx
0x14001fd69  jnz     loc_14001FE49
0x14001fd6f  mov     rcx, rsi; this
0x14001fd72  call    ?GetType@TpmResource@@QEBAIXZ; TpmResource::GetType(void)
0x14001fd77  cmp     [rsi+48h], ebx
0x14001fd7a  ja      loc_14001FE3D
0x14001fd80  test    ebp, ebp
0x14001fd82  jnz     short loc_14001FD8F
0x14001fd84  cmp     eax, r13d
0x14001fd87  jnz     loc_14001FE3D
0x14001fd8d  jmp     short loc_14001FD9D
0x14001fd8f  cmp     ebp, 1
0x14001fd92  jnz     short loc_14001FD9D
0x14001fd94  cmp     eax, 5
0x14001fd97  jz      loc_14001FE3D
0x14001fd9d  mov     rdx, r14; struct TpmResourceManager *
0x14001fda0  mov     rcx, rsi; this
0x14001fda3  call    ?Unload@TpmResource@@QEAAJPEAVTpmResourceManager@@@Z; TpmResource::Unload(TpmResourceManager *)
0x14001fda8  mov     edi, eax
0x14001fdaa  test    ebp, ebp
0x14001fdac  jnz     short loc_14001FDCD
0x14001fdae  mov     rcx, rsi; this
0x14001fdb1  call    ?GetType@TpmResource@@QEBAIXZ; TpmResource::GetType(void)
0x14001fdb6  cmp     eax, 2
0x14001fdb9  jnz     short loc_14001FDCD
0x14001fdbb  cmp     edi, 0C0290063h
0x14001fdc1  jnz     short loc_14001FDCD
0x14001fdc3  mov     rdx, r14; struct TpmResourceManager *
0x14001fdc6  call    ?Flush@TpmResource@@QEAAJPEAVTpmResourceManager@@@Z; TpmResource::Flush(TpmResourceManager *)
0x14001fdcb  mov     edi, eax
0x14001fdcd  test    edi, edi
0x14001fdcf  jns     short loc_14001FE38
0x14001fdd1  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001fdd8  lea     rcx, WPP_GLOBAL_Control
0x14001fddf  cmp     rax, rcx
0x14001fde2  jz      short loc_14001FE16
0x14001fde4  mov     eax, [rax+2Ch]
0x14001fde7  test    al, 2
0x14001fde9  jz      short loc_14001FE16
0x14001fdeb  mov     rcx, rsi; this
0x14001fdee  call    ?GetPhysicalHandle@TpmResource@@QEBAIXZ; TpmResource::GetPhysicalHandle(void)
0x14001fdf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fdfa  lea     r8, WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids
0x14001fe01  mov     edx, 0Fh
0x14001fe06  mov     [rsp+68h+var_48], edi
0x14001fe0a  mov     r9d, eax
0x14001fe0d  mov     rcx, [rcx+18h]
0x14001fe11  call    WPP_SF_Dd
0x14001fe16  mov     ecx, edi; int
0x14001fe18  call    ?IsTpmLowResourceStatus@TpmResourceManager@@CA_NJ@Z; TpmResourceManager::IsTpmLowResourceStatus(long)
0x14001fe1d  test    al, al
0x14001fe1f  jz      short loc_14001FE3D
0x14001fe21  mov     edx, 5; unsigned int
0x14001fe26  mov     rcx, r14; this
0x14001fe29  call    ?TrimResources@TpmResourceManager@@AEAAJI@Z; TpmResourceManager::TrimResources(uint)
0x14001fe2e  test    eax, eax
0x14001fe30  jns     loc_14001FD9D
0x14001fe36  jmp     short loc_14001FE3D
0x14001fe38  mov     ebx, 1
0x14001fe3d  mov     rsi, [rsi]
0x14001fe40  cmp     rsi, r15
0x14001fe43  jnz     loc_14001FD67
0x14001fe49  inc     ebp
0x14001fe4b  jmp     loc_14001FD4B
0x14001fe50  test    ebx, ebx
0x14001fe52  jnz     short loc_14001FE65
0x14001fe54  mov     edi, 0C0290011h
0x14001fe59  lea     rbp, WPP_GLOBAL_Control
0x14001fe60  jmp     loc_14001FEF0
0x14001fe65  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001fe6c  lea     rbp, WPP_GLOBAL_Control
0x14001fe73  cmp     rcx, rbp
0x14001fe76  jz      short loc_14001FE98
0x14001fe78  mov     eax, [rcx+2Ch]
0x14001fe7b  test    sil, al
0x14001fe7e  jz      short loc_14001FE98
0x14001fe80  mov     rcx, [rcx+18h]
0x14001fe84  lea     r8, WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids
0x14001fe8b  mov     edx, 10h
0x14001fe90  mov     r9d, ebx
0x14001fe93  call    WPP_SF_d
0x14001fe98  mov     qword ptr [rsp+68h+Interval], 0
0x14001fea1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001fea8  cmp     rcx, rbp
0x14001feab  jz      short loc_14001FECE
0x14001fead  mov     eax, [rcx+2Ch]
0x14001feb0  test    sil, al
0x14001feb3  jz      short loc_14001FECE
0x14001feb5  mov     rcx, [rcx+18h]
0x14001feb9  lea     r8, WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids
0x14001fec0  mov     edx, 11h
0x14001fec5  lea     r9d, [rdx-10h]
0x14001fec9  call    WPP_SF_d
0x14001fece  lea     r8, [rsp+68h+Interval]; Interval
0x14001fed3  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFFD8F0h
0x14001fedc  xor     edx, edx; Alertable
0x14001fede  xor     ecx, ecx; WaitMode
0x14001fee0  call    cs:__imp_KeDelayExecutionThread
0x14001fee7  nop     dword ptr [rax+rax+00h]
0x14001feec  test    edi, edi
0x14001feee  jns     short loc_14001FF1C
0x14001fef0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001fef7  cmp     rcx, rbp
0x14001fefa  jz      short loc_14001FF1C
0x14001fefc  mov     eax, [rcx+2Ch]
0x14001feff  test    sil, al
0x14001ff02  jz      short loc_14001FF1C
0x14001ff04  mov     rcx, [rcx+18h]
0x14001ff08  lea     r8, WPP_877edae9aa383c8b8ddc299c0d08a516_Traceguids
0x14001ff0f  mov     edx, 12h
0x14001ff14  mov     r9d, edi
0x14001ff17  call    WPP_SF_d
0x14001ff1c  mov     rbx, [rsp+68h+arg_10]
0x14001ff24  mov     eax, edi
0x14001ff26  add     rsp, 30h
0x14001ff2a  pop     r15
0x14001ff2c  pop     r14
0x14001ff2e  pop     r13
0x14001ff30  pop     r12
0x14001ff32  pop     rdi
0x14001ff33  pop     rsi
0x14001ff34  pop     rbp
0x14001ff35  retn
```
