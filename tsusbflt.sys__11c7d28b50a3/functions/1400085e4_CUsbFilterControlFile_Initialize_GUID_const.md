# CUsbFilterControlFile::Initialize(_GUID const *)

- ea: `0x1400085e4`
- end: `0x140008810`
- name: `?Initialize@CUsbFilterControlFile@@AEAAJPEBU_GUID@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CUsbFilterControlFile *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140006efc`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x140006128`
- `0x1400085e4`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000874a`
- `ntoskrnl!ObReferenceObjectByPointer` at `0x14000874a`
- `ntoskrnl!PsProcessType` at `0x140008735`
- `ntoskrnl!IoGetCurrentProcess` at `0x140008729`
- `ntoskrnl!IoGetCurrentProcess` at `0x140008729`
- `ntoskrnl!ObfDereferenceObject` at `0x14000878e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000878e`
- `ntoskrnl!RtlCheckTokenMembership` at `0x1400086fe`
- `ntoskrnl!RtlCheckTokenMembership` at `0x1400086fe`
- `ntoskrnl!SeExports` at `0x1400086db`

## pseudocode

```c
__int64 __fastcall CUsbFilterControlFile::Initialize(CUsbFilterControlFile *this, const struct _GUID *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // r9
  PEPROCESS CurrentProcess; // rsi
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  __int128 v11; // xmm0
  char v13; // [rsp+80h] [rbp+18h] BYREF

  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, CUsbFilterControlFile *))WPP_MAIN_CB.Queue.ListEntry.Flink[102].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         this);
  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[69].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         v4);
  v6 = *(unsigned int *)(((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                           WPP_MAIN_CB.Queue.ListEntry.Blink,
                           v5,
                           off_14000F068)
                       + 40);
  switch ( (_DWORD)v6 )
  {
    case 0:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
      goto LABEL_25;
    case 1:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
      v13 = 0;
      if ( (int)RtlCheckTokenMembership(0, SeExports->SeAliasAdminsSid, &v13) < 0 || v13 != 1 )
        goto LABEL_25;
      break;
    case 2:
      break;
    default:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, v6);
LABEL_25:
      v10 = -1073741790;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, 3221225506LL);
      return v10;
  }
  CurrentProcess = IoGetCurrentProcess();
  v9 = ObReferenceObjectByPointer(CurrentProcess, 0, (POBJECT_TYPE)PsProcessType, 0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *(_QWORD *)this = CurrentProcess;
    v10 = 0;
    v11 = (__int128)*a2;
    *((_BYTE *)this + 32) = 1;
    *((_OWORD *)this + 1) = v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
        CurrentProcess,
        v9);
    if ( CurrentProcess )
      ObfDereferenceObject(CurrentProcess);
  }
  return v10;
}

```

## disassembly

```asm
0x1400085e4  push    rbx
0x1400085e6  push    rbp
0x1400085e7  push    rsi
0x1400085e8  push    rdi
0x1400085e9  push    r14
0x1400085eb  push    r15
0x1400085ed  sub     rsp, 38h
0x1400085f1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400085f8  mov     rbp, rdx
0x1400085fb  mov     r14, rcx
0x1400085fe  mov     rdx, rcx
0x140008601  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008608  mov     rax, [rax+660h]
0x14000860f  call    _guard_dispatch_icall
0x140008614  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue
0x14000861b  mov     rdx, rax
0x14000861e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008625  mov     rax, [r8+458h]
0x14000862c  call    _guard_dispatch_icall
0x140008631  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140008638  mov     rdx, rax
0x14000863b  mov     r8, cs:off_14000F068
0x140008642  mov     rax, [rcx+650h]
0x140008649  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008650  call    _guard_dispatch_icall
0x140008655  lea     r15, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x14000865c  lea     rdi, WPP_GLOBAL_Control
0x140008663  mov     r9d, [rax+28h]
0x140008667  mov     ecx, r9d
0x14000866a  test    r9d, r9d
0x14000866d  jz      loc_1400087B2
0x140008673  sub     ecx, 1
0x140008676  jz      short loc_1400086B8
0x140008678  cmp     ecx, 1
0x14000867b  jz      loc_140008729
0x140008681  mov     rcx, cs:WPP_GLOBAL_Control
0x140008688  lea     rdi, WPP_GLOBAL_Control
0x14000868f  cmp     rcx, rdi
0x140008692  jz      loc_1400087D5
0x140008698  cmp     byte ptr [rcx+29h], 2
0x14000869c  jb      loc_1400087D5
0x1400086a2  mov     rcx, [rcx+18h]
0x1400086a6  mov     edx, 35h ; '5'
0x1400086ab  mov     r8, r15
0x1400086ae  call    WPP_SF_d
0x1400086b3  jmp     loc_1400087D5
0x1400086b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086bf  cmp     rcx, rdi
0x1400086c2  jz      short loc_1400086DB
0x1400086c4  cmp     byte ptr [rcx+29h], 5
0x1400086c8  jb      short loc_1400086DB
0x1400086ca  mov     rcx, [rcx+18h]
0x1400086ce  mov     edx, 34h ; '4'
0x1400086d3  mov     r8, r15
0x1400086d6  call    WPP_SF_
0x1400086db  mov     rax, cs:__imp_SeExports
0x1400086e2  lea     r8, [rsp+68h+arg_10]
0x1400086ea  xor     ecx, ecx
0x1400086ec  mov     [rsp+68h+arg_10], 0
0x1400086f4  mov     rdx, [rax]
0x1400086f7  mov     rdx, [rdx+110h]
0x1400086fe  call    cs:__imp_RtlCheckTokenMembership
0x140008705  nop     dword ptr [rax+rax+00h]
0x14000870a  test    eax, eax
0x14000870c  js      short loc_14000871F
0x14000870e  cmp     [rsp+68h+arg_10], 1
0x140008716  jnz     short loc_14000871F
0x140008718  mov     eax, 1
0x14000871d  jmp     short loc_140008721
0x14000871f  xor     eax, eax
0x140008721  test    eax, eax
0x140008723  jz      loc_1400087D5
0x140008729  call    cs:__imp_IoGetCurrentProcess
0x140008730  nop     dword ptr [rax+rax+00h]
0x140008735  mov     r8, cs:__imp_PsProcessType
0x14000873c  xor     r9d, r9d; AccessMode
0x14000873f  xor     edx, edx; DesiredAccess
0x140008741  mov     rcx, rax; Object
0x140008744  mov     rsi, rax
0x140008747  mov     r8, [r8]; ObjectType
0x14000874a  call    cs:__imp_ObReferenceObjectByPointer
0x140008751  nop     dword ptr [rax+rax+00h]
0x140008756  mov     ebx, eax
0x140008758  test    eax, eax
0x14000875a  jns     short loc_14000879C
0x14000875c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008763  cmp     rcx, rdi
0x140008766  jz      short loc_140008786
0x140008768  cmp     byte ptr [rcx+29h], 2
0x14000876c  jb      short loc_140008786
0x14000876e  mov     rcx, [rcx+18h]
0x140008772  mov     edx, 32h ; '2'
0x140008777  mov     r9, rsi
0x14000877a  mov     [rsp+68h+var_48], eax
0x14000877e  mov     r8, r15
0x140008781  call    WPP_SF_qd
0x140008786  test    rsi, rsi
0x140008789  jz      short loc_140008800
0x14000878b  mov     rcx, rsi; Object
0x14000878e  call    cs:__imp_ObfDereferenceObject
0x140008795  nop     dword ptr [rax+rax+00h]
0x14000879a  jmp     short loc_140008800
0x14000879c  mov     [r14], rsi
0x14000879f  xor     ebx, ebx
0x1400087a1  movups  xmm0, xmmword ptr [rbp+0]
0x1400087a5  mov     byte ptr [r14+20h], 1
0x1400087aa  movdqu  xmmword ptr [r14+10h], xmm0
0x1400087b0  jmp     short loc_140008800
0x1400087b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087b9  cmp     rcx, rdi
0x1400087bc  jz      short loc_1400087D5
0x1400087be  cmp     byte ptr [rcx+29h], 2
0x1400087c2  jb      short loc_1400087D5
0x1400087c4  mov     rcx, [rcx+18h]
0x1400087c8  mov     edx, 33h ; '3'
0x1400087cd  mov     r8, r15
0x1400087d0  call    WPP_SF_
0x1400087d5  mov     ebx, 0C0000022h
0x1400087da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087e1  cmp     rcx, rdi
0x1400087e4  jz      short loc_140008800
0x1400087e6  cmp     byte ptr [rcx+29h], 2
0x1400087ea  jb      short loc_140008800
0x1400087ec  mov     rcx, [rcx+18h]
0x1400087f0  mov     edx, 31h ; '1'
0x1400087f5  mov     r9d, ebx
0x1400087f8  mov     r8, r15
0x1400087fb  call    WPP_SF_d
0x140008800  mov     eax, ebx
0x140008802  add     rsp, 38h
0x140008806  pop     r15
0x140008808  pop     r14
0x14000880a  pop     rdi
0x14000880b  pop     rsi
0x14000880c  pop     rbp
0x14000880d  pop     rbx
0x14000880e  retn
```
