# TmpCreateInternalCrmEnlistment

- ea: `0x1400153b8`
- end: `0x140015641`
- name: `TmpCreateInternalCrmEnlistment`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140015c8c`

## callees

- `0x1400153b8`
- `0x1400162e4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400155fb`
- `ntoskrnl!ObfDereferenceObject` at `0x140022548`
- `ntoskrnl!ObfDereferenceObject` at `0x1400155fb`
- `ntoskrnl!ObfDereferenceObject` at `0x140022548`
- `ntoskrnl!ZwClose` at `0x1400155e3`
- `ntoskrnl!ZwClose` at `0x140015612`
- `ntoskrnl!ZwClose` at `0x140022525`
- `ntoskrnl!ZwClose` at `0x14002256b`
- `ntoskrnl!ZwClose` at `0x1400155e3`
- `ntoskrnl!ZwClose` at `0x140015612`
- `ntoskrnl!ZwClose` at `0x140022525`
- `ntoskrnl!ZwClose` at `0x14002256b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001543d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001543d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001550a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001550a`
- `ntoskrnl!ZwCreateEnlistment` at `0x1400154cd`
- `ntoskrnl!ZwCreateEnlistment` at `0x1400154cd`
- `ntoskrnl!SeSystemDefaultSd` at `0x14001548a`

## pseudocode

```c
__int64 __fastcall TmpCreateInternalCrmEnlistment(
        void *a1,
        __int64 a2,
        ULONG a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PVOID *a7,
        PHANDLE EnlistmentHandle)
{
  NTSTATUS v11; // esi
  void *v12; // rcx
  PVOID v13; // rcx
  HANDLE TransactionHandle; // [rsp+48h] [rbp-70h] BYREF
  PVOID Object; // [rsp+50h] [rbp-68h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-60h] BYREF
  char v18; // [rsp+D0h] [rbp+18h]

  v18 = a3;
  memset(&ObjectAttributes, 0, 44);
  TransactionHandle = 0;
  *EnlistmentHandle = 0;
  *a7 = 0;
  v11 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x1F003Fu, (POBJECT_TYPE)TmTransactionObjectType, 0, &TransactionHandle);
  if ( v11 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    ObjectAttributes.SecurityDescriptor = (PVOID)SeSystemDefaultSd;
    ObjectAttributes.SecurityQualityOfService = 0;
    v11 = ZwCreateEnlistment(
            EnlistmentHandle,
            0xF001Fu,
            *(HANDLE *)(a2 + 672),
            TransactionHandle,
            &ObjectAttributes,
            a3,
            (v18 & 1) != 0 ? 553648248 : 527,
            0);
    if ( v11 >= 0 )
    {
      v12 = *EnlistmentHandle;
      Object = 0;
      v11 = ObReferenceObjectByHandle(v12, 0, (POBJECT_TYPE)TmEnlistmentObjectType, 0, &Object, 0);
      v13 = Object;
      *a7 = Object;
      if ( v11 >= 0 )
      {
        if ( a5 )
        {
          TmpInternalCrmLinkEnlistment(v13, a4);
          TmpInternalCrmLinkEnlistment(a4, *a7);
          if ( (*((_DWORD *)*a7 + 43) & 2) == 0 && (*(_DWORD *)(a4 + 172) & 2) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)(a4 + 172), 0xFFFFFFFD);
            --*(_DWORD *)(*(_QWORD *)(a4 + 160) + 220LL);
          }
          if ( (*((_DWORD *)*a7 + 43) & 2) != 0 && (*(_DWORD *)(a4 + 172) & 2) == 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)*a7 + 43, 0xFFFFFFFD);
            --*(_DWORD *)(*((_QWORD *)*a7 + 20) + 220LL);
          }
          if ( (v18 & 1) != 0 )
            *((_QWORD *)*a7 + 32) = a6;
          else
            *(_QWORD *)(a4 + 256) = a6;
        }
      }
    }
  }
  if ( TransactionHandle )
    ZwClose(TransactionHandle);
  if ( v11 < 0 )
  {
    if ( *a7 )
    {
      ObfDereferenceObject(*a7);
      *a7 = 0;
    }
    if ( *EnlistmentHandle )
    {
      ZwClose(*EnlistmentHandle);
      *EnlistmentHandle = 0;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400153b8  mov     r11, rsp
0x1400153bb  mov     [r11+8], rbx
0x1400153bf  mov     [r11+10h], rsi
0x1400153c3  mov     [r11+18h], r8d
0x1400153c7  push    rdi
0x1400153c8  push    r12
0x1400153ca  push    r13
0x1400153cc  push    r14
0x1400153ce  push    r15
0x1400153d0  sub     rsp, 90h
0x1400153d7  mov     rdi, r9
0x1400153da  mov     r15d, r8d
0x1400153dd  mov     r13, rdx
0x1400153e0  xor     eax, eax
0x1400153e2  xorps   xmm0, xmm0
0x1400153e5  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x1400153ea  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x1400153ef  movups  xmmword ptr [rsp+0B8h+ObjectAttributes+1Ch], xmm0
0x1400153f4  xor     r12d, r12d
0x1400153f7  mov     [r11-70h], r12
0x1400153fb  mov     [r11-78h], r12d
0x1400153ff  mov     r14, [rsp+0B8h+EnlistmentHandle]
0x140015407  mov     [r14], r12
0x14001540a  mov     rbx, [rsp+0B8h+arg_30]
0x140015412  mov     [rbx], r12
0x140015415  lea     rax, [r11-70h]
0x140015419  mov     [rsp+0B8h+Handle], rax; Handle
0x14001541e  mov     [rsp+0B8h+AccessMode], r12b; AccessMode
0x140015423  mov     rax, cs:TmTransactionObjectType
0x14001542a  mov     [rsp+0B8h+ObjectType], rax; ObjectType
0x14001542f  mov     r9d, 1F003Fh; DesiredAccess
0x140015435  xor     r8d, r8d; PassedAccessState
0x140015438  mov     edx, 200h; HandleAttributes
0x14001543d  call    cs:__imp_ObOpenObjectByPointer
0x140015444  nop     dword ptr [rax+rax+00h]
0x140015449  mov     esi, eax
0x14001544b  mov     [rsp+0B8h+var_78], eax
0x14001544f  test    eax, eax
0x140015451  js      loc_1400155D9
0x140015457  mov     eax, [rsp+0B8h+arg_10]
0x14001545e  and     al, 1
0x140015460  neg     al
0x140015462  sbb     edx, edx
0x140015464  and     edx, 20FFFE69h
0x14001546a  add     edx, 20Fh
0x140015470  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x140015478  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], r12
0x14001547d  mov     [rsp+0B8h+ObjectAttributes.Attributes], 200h
0x140015485  mov     [rsp+0B8h+ObjectAttributes.ObjectName], r12
0x14001548a  mov     rax, cs:__imp_SeSystemDefaultSd
0x140015491  mov     rcx, [rax]
0x140015494  mov     [rsp+0B8h+ObjectAttributes.SecurityDescriptor], rcx
0x140015499  mov     [rsp+0B8h+ObjectAttributes.SecurityQualityOfService], r12
0x1400154a1  mov     [rsp+0B8h+EnlistmentKey], r12; EnlistmentKey
0x1400154a6  mov     dword ptr [rsp+0B8h+Handle], edx; NotificationMask
0x1400154aa  mov     dword ptr [rsp+0B8h+AccessMode], r15d; CreateOptions
0x1400154af  lea     rax, [rsp+0B8h+ObjectAttributes]
0x1400154b4  mov     [rsp+0B8h+ObjectType], rax; ObjectAttributes
0x1400154b9  mov     r9, [rsp+0B8h+TransactionHandle]; TransactionHandle
0x1400154be  mov     r8, [r13+2A0h]; ResourceManagerHandle
0x1400154c5  mov     edx, 0F001Fh; DesiredAccess
0x1400154ca  mov     rcx, r14; EnlistmentHandle
0x1400154cd  call    cs:__imp_ZwCreateEnlistment
0x1400154d4  nop     dword ptr [rax+rax+00h]
0x1400154d9  mov     esi, eax
0x1400154db  mov     [rsp+0B8h+var_78], eax
0x1400154df  test    eax, eax
0x1400154e1  js      loc_1400155D9
0x1400154e7  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x1400154ee  mov     rcx, [r14]; Handle
0x1400154f1  mov     [rsp+0B8h+Object], r12
0x1400154f6  mov     qword ptr [rsp+0B8h+AccessMode], r12; HandleInformation
0x1400154fb  lea     rax, [rsp+0B8h+Object]
0x140015500  mov     [rsp+0B8h+ObjectType], rax; Object
0x140015505  xor     r9d, r9d; AccessMode
0x140015508  xor     edx, edx; DesiredAccess
0x14001550a  call    cs:__imp_ObReferenceObjectByHandle
0x140015511  nop     dword ptr [rax+rax+00h]
0x140015516  mov     esi, eax
0x140015518  mov     rcx, [rsp+0B8h+Object]
0x14001551d  mov     [rbx], rcx
0x140015520  mov     [rsp+0B8h+var_78], eax
0x140015524  test    eax, eax
0x140015526  js      loc_1400155D9
0x14001552c  mov     r8, [rsp+0B8h+arg_20]
0x140015534  test    r8, r8
0x140015537  jz      loc_1400155D9
0x14001553d  mov     rdx, rdi
0x140015540  call    TmpInternalCrmLinkEnlistment
0x140015545  mov     r8, [r14]
0x140015548  mov     rdx, [rbx]
0x14001554b  mov     rcx, rdi
0x14001554e  call    TmpInternalCrmLinkEnlistment
0x140015553  mov     rcx, [rbx]
0x140015556  mov     eax, [rcx+0ACh]
0x14001555c  mov     dl, 2
0x14001555e  test    dl, al
0x140015560  jnz     short loc_140015581
0x140015562  mov     eax, [rdi+0ACh]
0x140015568  test    dl, al
0x14001556a  jz      short loc_140015581
0x14001556c  lock and dword ptr [rdi+0ACh], 0FFFFFFFDh
0x140015574  mov     rax, [rdi+0A0h]
0x14001557b  dec     dword ptr [rax+0DCh]
0x140015581  mov     rax, [rbx]
0x140015584  mov     ecx, [rax+0ACh]
0x14001558a  test    dl, cl
0x14001558c  jz      short loc_1400155B3
0x14001558e  mov     eax, [rdi+0ACh]
0x140015594  test    dl, al
0x140015596  jnz     short loc_1400155B3
0x140015598  mov     rax, [rbx]
0x14001559b  lock and dword ptr [rax+0ACh], 0FFFFFFFDh
0x1400155a3  mov     rax, [rbx]
0x1400155a6  mov     rcx, [rax+0A0h]
0x1400155ad  dec     dword ptr [rcx+0DCh]
0x1400155b3  mov     eax, [rsp+0B8h+arg_10]
0x1400155ba  test    al, 1
0x1400155bc  mov     rax, [rsp+0B8h+arg_28]
0x1400155c4  jz      short loc_1400155D2
0x1400155c6  mov     rcx, [rbx]
0x1400155c9  mov     [rcx+100h], rax
0x1400155d0  jmp     short loc_1400155D9
0x1400155d2  mov     [rdi+100h], rax
0x1400155d9  mov     rcx, [rsp+0B8h+TransactionHandle]; Handle
0x1400155de  test    rcx, rcx
0x1400155e1  jz      short loc_1400155EF
0x1400155e3  call    cs:__imp_ZwClose
0x1400155ea  nop     dword ptr [rax+rax+00h]
0x1400155ef  test    esi, esi
0x1400155f1  jns     short loc_140015621
0x1400155f3  mov     rcx, [rbx]; Object
0x1400155f6  test    rcx, rcx
0x1400155f9  jz      short loc_14001560A
0x1400155fb  call    cs:__imp_ObfDereferenceObject
0x140015602  nop     dword ptr [rax+rax+00h]
0x140015607  mov     [rbx], r12
0x14001560a  mov     rcx, [r14]; Handle
0x14001560d  test    rcx, rcx
0x140015610  jz      short loc_140015621
0x140015612  call    cs:__imp_ZwClose
0x140015619  nop     dword ptr [rax+rax+00h]
0x14001561e  mov     [r14], r12
0x140015621  mov     eax, esi
0x140015623  lea     r11, [rsp+0B8h+var_28]
0x14001562b  mov     rbx, [r11+30h]
0x14001562f  mov     rsi, [r11+38h]
0x140015633  mov     rsp, r11
0x140015636  pop     r15
0x140015638  pop     r14
0x14001563a  pop     r13
0x14001563c  pop     r12
0x14001563e  pop     rdi
0x14001563f  retn
0x140022512  push    rbx
0x140022514  push    rbp
0x140022515  sub     rsp, 48h
0x140022519  mov     rbp, rdx
0x14002251c  mov     rcx, [rbp+48h]; Handle
0x140022520  test    rcx, rcx
0x140022523  jz      short loc_140022532
0x140022525  call    cs:__imp_ZwClose
0x14002252c  nop     dword ptr [rax+rax+00h]
0x140022531  nop
0x140022532  cmp     dword ptr [rbp+40h], 0
0x140022536  jge     short loc_14002257E
0x140022538  mov     rbx, [rbp+0F0h]
0x14002253f  cmp     qword ptr [rbx], 0
0x140022543  jz      short loc_14002255B
0x140022545  mov     rcx, [rbx]; Object
0x140022548  call    cs:__imp_ObfDereferenceObject
0x14002254f  nop     dword ptr [rax+rax+00h]
0x140022554  mov     qword ptr [rbx], 0
0x14002255b  mov     rbx, [rbp+0F8h]
0x140022562  cmp     qword ptr [rbx], 0
0x140022566  jz      short loc_14002257E
0x140022568  mov     rcx, [rbx]; Handle
0x14002256b  call    cs:__imp_ZwClose
0x140022572  nop     dword ptr [rax+rax+00h]
0x140022577  mov     qword ptr [rbx], 0
0x14002257e  add     rsp, 48h
0x140022582  pop     rbp
0x140022583  pop     rbx
0x140022584  retn
```
