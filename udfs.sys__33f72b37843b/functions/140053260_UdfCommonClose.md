# UdfCommonClose

- ea: `0x140053260`
- end: `0x1400534c8`
- name: `UdfCommonClose`
- size: `616`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140008594`
- `0x140010c5c`
- `0x140053260`
- `0x1400534d0`
- `0x1400541a8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400532f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400532f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053390`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005349f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053390`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005349f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400533e6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400533e6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140053315`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140053315`

## pseudocode

```c
__int64 __fastcall UdfCommonClose(_QWORD *Entry, IRP *a2)
{
  _DWORD *v3; // rdi
  PFILE_OBJECT FileObject; // rcx
  unsigned __int64 FsContext2; // rbx
  int v6; // r14d
  _QWORD *v7; // rbx
  int v8; // r12d
  _QWORD *FsContext; // r15
  __int64 v10; // rbp
  void *v11; // rcx
  int v12; // ecx
  char v13; // bl

  v3 = Entry;
  if ( !Entry[2]
    || (FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject,
        FsContext2 = (unsigned __int64)FileObject->FsContext2,
        FileObject->FsContext2 = (PVOID)FsContext2,
        v6 = FsContext2 & 7,
        (FsContext2 & 7) == 0) )
  {
    UdfCompleteRequest(v3, a2, 0);
    return 0;
  }
  v7 = (_QWORD *)(FsContext2 & 0xFFFFFFFFFFFFFFF8uLL);
  v8 = 0;
  FsContext = FileObject->FsContext;
  v10 = *(_QWORD *)(FsContext[17] + 8LL);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 8) != 0 )
  {
    WPP_SF_qq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      12,
      WPP_48d000ed1a6b379815b8d910c350b5ab_Traceguids,
      a2->Tail.Overlay.CurrentStackLocation->FileObject,
      FsContext);
  }
  if ( v7 )
  {
    v11 = (void *)v7[6];
    v8 = 1;
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0);
      v7[6] = 0;
    }
    ExFreeToPagedLookasideList(&UdfCcbLookasideList, v7);
  }
  v12 = *(_DWORD *)(v10 + 52);
  if ( v12 == 2
    && *((_DWORD *)FsContext + 51) == 1
    && (*((_DWORD *)FsContext + 53) & 0x200) == 0
    && !*((_DWORD *)FsContext + 54)
    && (unsigned int)(v6 - 3) <= 1 )
  {
    UdfQueueClose(v3);
    UdfCompleteRequest(0, a2, 0);
    return 0;
  }
  v13 = 0;
  if ( !*(_DWORD *)(v10 + 252) && v12 != 2 )
  {
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( *(_DWORD *)(v10 + 252) || (unsigned int)(*(_DWORD *)(v10 + 52) - 1) <= 1 || (v3[7] & 0x20) == 0 )
      ExReleaseResourceLite(&Resource);
    else
      v13 = 1;
  }
  if ( !(unsigned __int8)UdfCommonClosePrivate((_DWORD)v3, v10, (_DWORD)FsContext, v8, 1) )
  {
    UdfQueueClose(v3);
    v3 = 0;
LABEL_18:
    UdfCompleteRequest(v3, a2, 0);
    if ( !v13 )
      return 0;
    goto LABEL_17;
  }
  if ( !v13 )
    goto LABEL_18;
  UdfCheckForDismount(v3, v10, 0);
  UdfCompleteRequest(v3, a2, 0);
LABEL_17:
  ExReleaseResourceLite(&Resource);
  return 0;
}

```

## disassembly

```asm
0x140053260  mov     [rsp+arg_18], rbx
0x140053265  push    rsi
0x140053266  push    rdi
0x140053267  push    r14
0x140053269  sub     rsp, 30h
0x14005326d  cmp     qword ptr [rcx+10h], 0
0x140053272  mov     rsi, rdx
0x140053275  mov     rdi, rcx
0x140053278  jz      loc_1400533D0
0x14005327e  mov     rax, [rdx+0B8h]
0x140053285  mov     rcx, [rax+30h]
0x140053289  mov     rbx, [rcx+20h]
0x14005328d  mov     r14d, ebx
0x140053290  mov     [rcx+20h], rbx
0x140053294  and     r14d, 7
0x140053298  jz      loc_1400533D0
0x14005329e  mov     [rsp+48h+arg_0], rbp
0x1400532a3  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400532a7  mov     [rsp+48h+arg_8], r12
0x1400532ac  xor     r12d, r12d
0x1400532af  mov     [rsp+48h+arg_10], r15
0x1400532b4  mov     r15, [rcx+18h]
0x1400532b8  mov     rax, [r15+88h]
0x1400532bf  mov     rbp, [rax+8]
0x1400532c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400532ca  lea     rax, WPP_GLOBAL_Control
0x1400532d1  cmp     rcx, rax
0x1400532d4  jz      short loc_1400532E1
0x1400532d6  mov     eax, [rcx+2Ch]
0x1400532d9  test    al, 8
0x1400532db  jnz     loc_14005346E
0x1400532e1  test    rbx, rbx
0x1400532e4  jz      short loc_140053321
0x1400532e6  mov     rcx, [rbx+30h]; P
0x1400532ea  mov     r12d, 1
0x1400532f0  test    rcx, rcx
0x1400532f3  jz      short loc_14005330B
0x1400532f5  xor     edx, edx; Tag
0x1400532f7  call    cs:__imp_ExFreePoolWithTag
0x1400532fe  nop     dword ptr [rax+rax+00h]
0x140053303  mov     qword ptr [rbx+30h], 0
0x14005330b  mov     rdx, rbx; Entry
0x14005330e  lea     rcx, UdfCcbLookasideList; Lookaside
0x140053315  call    cs:__imp_ExFreeToPagedLookasideList
0x14005331c  nop     dword ptr [rax+rax+00h]
0x140053321  mov     ecx, [rbp+34h]
0x140053324  cmp     ecx, 2
0x140053327  jnz     short loc_140053337
0x140053329  cmp     dword ptr [r15+0CCh], 1
0x140053331  jz      loc_14005341F
0x140053337  xor     bl, bl
0x140053339  cmp     dword ptr [rbp+0FCh], 0
0x140053340  jnz     short loc_14005334B
0x140053342  cmp     ecx, 2
0x140053345  jnz     loc_1400533DD
0x14005334b  mov     r9d, r12d
0x14005334e  mov     byte ptr [rsp+48h+var_28], 1
0x140053353  mov     r8, r15
0x140053356  mov     rdx, rbp
0x140053359  mov     rcx, rdi
0x14005335c  call    UdfCommonClosePrivate
0x140053361  test    al, al
0x140053363  jz      loc_1400534B0
0x140053369  test    bl, bl
0x14005336b  jz      short loc_14005339E
0x14005336d  xor     r8d, r8d
0x140053370  mov     rdx, rbp
0x140053373  mov     rcx, rdi
0x140053376  call    UdfCheckForDismount
0x14005337b  xor     r8d, r8d
0x14005337e  mov     rdx, rsi
0x140053381  mov     rcx, rdi
0x140053384  call    UdfCompleteRequest
0x140053389  lea     rcx, Resource; Resource
0x140053390  call    cs:__imp_ExReleaseResourceLite
0x140053397  nop     dword ptr [rax+rax+00h]
0x14005339c  jmp     short loc_1400533B0
0x14005339e  xor     r8d, r8d
0x1400533a1  mov     rdx, rsi
0x1400533a4  mov     rcx, rdi
0x1400533a7  call    UdfCompleteRequest
0x1400533ac  test    bl, bl
0x1400533ae  jnz     short loc_140053389
0x1400533b0  mov     r15, [rsp+48h+arg_10]
0x1400533b5  mov     r12, [rsp+48h+arg_8]
0x1400533ba  mov     rbp, [rsp+48h+arg_0]
0x1400533bf  mov     rbx, [rsp+48h+arg_18]
0x1400533c4  xor     eax, eax
0x1400533c6  add     rsp, 30h
0x1400533ca  pop     r14
0x1400533cc  pop     rdi
0x1400533cd  pop     rsi
0x1400533ce  retn
0x1400533d0  xor     r8d, r8d
0x1400533d3  mov     rcx, rdi
0x1400533d6  call    UdfCompleteRequest
0x1400533db  jmp     short loc_1400533BF
0x1400533dd  mov     dl, 1; Wait
0x1400533df  lea     rcx, Resource; Resource
0x1400533e6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400533ed  nop     dword ptr [rax+rax+00h]
0x1400533f2  cmp     dword ptr [rbp+0FCh], 0
0x1400533f9  jnz     loc_140053498
0x1400533ff  mov     eax, [rbp+34h]
0x140053402  dec     eax
0x140053404  cmp     eax, 1
0x140053407  jbe     loc_140053498
0x14005340d  mov     eax, [rdi+1Ch]
0x140053410  test    al, 20h
0x140053412  jz      loc_140053498
0x140053418  mov     bl, 1
0x14005341a  jmp     loc_14005334B
0x14005341f  test    dword ptr [r15+0D4h], 200h
0x14005342a  jnz     loc_140053337
0x140053430  cmp     dword ptr [r15+0D8h], 0
0x140053438  jnz     loc_140053337
0x14005343e  lea     eax, [r14-3]
0x140053442  cmp     eax, 1
0x140053445  ja      loc_140053337
0x14005344b  mov     r9b, 1
0x14005344e  mov     r8d, r12d
0x140053451  mov     rdx, r15
0x140053454  mov     rcx, rdi; Entry
0x140053457  call    UdfQueueClose
0x14005345c  xor     r8d, r8d
0x14005345f  mov     rdx, rsi
0x140053462  xor     ecx, ecx
0x140053464  call    UdfCompleteRequest
0x140053469  jmp     loc_1400533B0
0x14005346e  mov     r9, [rdx+0B8h]
0x140053475  lea     r8, WPP_48d000ed1a6b379815b8d910c350b5ab_Traceguids
0x14005347c  mov     rcx, [rcx+18h]
0x140053480  mov     edx, 0Ch
0x140053485  mov     [rsp+48h+var_28], r15
0x14005348a  mov     r9, [r9+30h]
0x14005348e  call    WPP_SF_qq
0x140053493  jmp     loc_1400532E1
0x140053498  lea     rcx, Resource; Resource
0x14005349f  call    cs:__imp_ExReleaseResourceLite
0x1400534a6  nop     dword ptr [rax+rax+00h]
0x1400534ab  jmp     loc_14005334B
0x1400534b0  xor     r9d, r9d
0x1400534b3  mov     r8d, r12d
0x1400534b6  mov     rdx, r15
0x1400534b9  mov     rcx, rdi; Entry
0x1400534bc  call    UdfQueueClose
0x1400534c1  xor     edi, edi
0x1400534c3  jmp     loc_14005339E
```
