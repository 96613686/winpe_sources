# CPXWizardRegistration::UnregisterTask(_GUID const *,_GUID const *,int)

- ea: `0x180007730`
- end: `0x1800077c3`
- name: `?UnregisterTask@CPXWizardRegistration@@UEAAJPEBU_GUID@@0H@Z`
- size: `147`
- prototype: `int(CPXWizardRegistration *__hidden this, const struct _GUID *, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007730`
- `0x180007820`
- `0x180009ca0`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistration::UnregisterTask(
        CPXWizardRegistration *this,
        struct _GUID *a2,
        struct _GUID *a3,
        int a4)
{
  struct _GUID *v4; // r10
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int v7; // ebx

  v4 = a3;
  if ( a2 )
  {
    v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v5 )
      a2 = 0;
  }
  if ( a3 )
  {
    v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v6 )
      v4 = 0;
  }
  v7 = HrUnregisterWizardComponent(v4, a2, a4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180007730  push    rbx
0x180007732  sub     rsp, 20h
0x180007736  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x18000773d  mov     r10, r8
0x180007740  mov     r8, qword ptr cs:GUID_NULL.Data4
0x180007747  test    rdx, rdx
0x18000774a  jz      short loc_180007762
0x18000774c  mov     rax, [rdx]
0x18000774f  sub     rax, rcx
0x180007752  jnz     short loc_18000775B
0x180007754  mov     rax, [rdx+8]
0x180007758  sub     rax, r8
0x18000775b  test    rax, rax
0x18000775e  jnz     short loc_180007762
0x180007760  xor     edx, edx; struct _GUID *
0x180007762  test    r10, r10
0x180007765  jz      short loc_18000777E
0x180007767  mov     rax, [r10]
0x18000776a  sub     rax, rcx
0x18000776d  jnz     short loc_180007776
0x18000776f  mov     rax, [r10+8]
0x180007773  sub     rax, r8
0x180007776  test    rax, rax
0x180007779  jnz     short loc_18000777E
0x18000777b  xor     r10d, r10d
0x18000777e  mov     r8d, r9d; int
0x180007781  mov     rcx, r10; struct _GUID *
0x180007784  call    ?HrUnregisterWizardComponent@@YAJPEBU_GUID@@0H@Z; HrUnregisterWizardComponent(_GUID const *,_GUID const *,int)
0x180007789  mov     ebx, eax
0x18000778b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007792  lea     rax, WPP_GLOBAL_Control
0x180007799  cmp     rcx, rax
0x18000779c  jz      short loc_1800077BB
0x18000779e  mov     edx, 10h
0x1800077a3  test    [rcx+1Ch], dl
0x1800077a6  jz      short loc_1800077BB
0x1800077a8  mov     rcx, [rcx+10h]
0x1800077ac  lea     r8, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids
0x1800077b3  mov     r9d, ebx
0x1800077b6  call    WPP_SF_D
0x1800077bb  mov     eax, ebx
0x1800077bd  add     rsp, 20h
0x1800077c1  pop     rbx
0x1800077c2  retn
```
