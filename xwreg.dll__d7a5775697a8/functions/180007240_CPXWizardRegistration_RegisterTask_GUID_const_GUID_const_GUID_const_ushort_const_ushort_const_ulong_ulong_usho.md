# CPXWizardRegistration::RegisterTask(_GUID const *,_GUID const *,_GUID const *,ushort * const,ushort * const,ulong,ulong,ushort * const,ulong,unsigned __int64)

- ea: `0x180007240`
- end: `0x180007379`
- name: `?RegisterTask@CPXWizardRegistration@@UEAAJPEBU_GUID@@00QEAG1KK1K_K@Z`
- size: `313`
- prototype: `__int64 __fastcall(CPXWizardRegistration *__hidden this, const struct _GUID *, const struct _GUID *, const struct _GUID *, unsigned __int16 *const, unsigned __int16 *const, unsigned int, unsigned int, unsigned __int16 *const, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007240`
- `0x180007820`
- `0x1800085ac`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistration::RegisterTask(
        CPXWizardRegistration *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        struct _GUID *a4,
        unsigned __int16 *const a5,
        unsigned __int16 *const a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int16 *const a9,
        DWORD a10,
        void *a11)
{
  unsigned __int16 *v11; // r11
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // ebx

  v11 = a9;
  if ( a9 && !*a9 )
    v11 = 0;
  v14 = a6;
  if ( a6 && !*a6 )
    v14 = 0;
  v15 = a5;
  if ( a5 && !*a5 )
    v15 = 0;
  if ( a4 )
  {
    v16 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v16 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v16 )
      a4 = 0;
  }
  if ( a2 )
  {
    v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v17 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v17 )
      a2 = 0;
  }
  v18 = HrRegisterWizardComponent(2u, a3, 1u, a2, a4, (__int64)v15, (__int64)v14, a7, a8, (__int64)v11, a10, a11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids, v18);
  return v18;
}

```

## disassembly

```asm
0x180007240  mov     [rsp+arg_0], rbx
0x180007245  mov     [rsp+arg_8], rsi
0x18000724a  push    rdi
0x18000724b  sub     rsp, 60h
0x18000724f  mov     r11, [rsp+68h+arg_40]
0x180007257  xor     esi, esi
0x180007259  mov     r10, r9
0x18000725c  mov     rdi, r8
0x18000725f  mov     r9, rdx
0x180007262  test    r11, r11
0x180007265  jz      short loc_180007270
0x180007267  cmp     [r11], si
0x18000726b  jnz     short loc_180007270
0x18000726d  mov     r11d, esi
0x180007270  mov     rcx, [rsp+68h+arg_28]
0x180007278  test    rcx, rcx
0x18000727b  jz      short loc_180007285
0x18000727d  cmp     [rcx], si
0x180007280  jnz     short loc_180007285
0x180007282  mov     rcx, rsi
0x180007285  mov     rdx, [rsp+68h+arg_20]
0x18000728d  test    rdx, rdx
0x180007290  jz      short loc_18000729A
0x180007292  cmp     [rdx], si
0x180007295  jnz     short loc_18000729A
0x180007297  mov     rdx, rsi
0x18000729a  mov     rbx, qword ptr cs:GUID_NULL.Data4
0x1800072a1  mov     r8, qword ptr cs:GUID_NULL.Data1
0x1800072a8  test    r10, r10
0x1800072ab  jz      short loc_1800072C4
0x1800072ad  mov     rax, [r10]
0x1800072b0  sub     rax, r8
0x1800072b3  jnz     short loc_1800072BC
0x1800072b5  mov     rax, [r10+8]
0x1800072b9  sub     rax, rbx
0x1800072bc  test    rax, rax
0x1800072bf  jnz     short loc_1800072C4
0x1800072c1  mov     r10, rsi
0x1800072c4  test    r9, r9
0x1800072c7  jz      short loc_1800072E0
0x1800072c9  mov     rax, [r9]
0x1800072cc  sub     rax, r8
0x1800072cf  jnz     short loc_1800072D8
0x1800072d1  mov     rax, [r9+8]
0x1800072d5  sub     rax, rbx
0x1800072d8  test    rax, rax
0x1800072db  jnz     short loc_1800072E0
0x1800072dd  mov     r9, rsi
0x1800072e0  mov     rax, [rsp+68h+arg_50]
0x1800072e8  mov     r8d, 1
0x1800072ee  mov     [rsp+68h+var_10], rax
0x1800072f3  mov     eax, [rsp+68h+arg_48]
0x1800072fa  mov     [rsp+68h+var_18], eax
0x1800072fe  mov     eax, [rsp+68h+arg_38]
0x180007305  mov     [rsp+68h+var_20], r11
0x18000730a  mov     [rsp+68h+var_28], eax
0x18000730e  mov     eax, [rsp+68h+arg_30]
0x180007315  mov     [rsp+68h+var_30], eax
0x180007319  mov     [rsp+68h+var_38], rcx
0x18000731e  lea     ecx, [r8+1]
0x180007322  mov     [rsp+68h+var_40], rdx
0x180007327  mov     rdx, rdi
0x18000732a  mov     [rsp+68h+var_48], r10
0x18000732f  call    ?HrRegisterWizardComponent@@YAJW4tagXW_COMPONENT_TYPE@@PEBU_GUID@@011QEAG2KK2KQEAX@Z; HrRegisterWizardComponent(tagXW_COMPONENT_TYPE,_GUID const *,tagXW_COMPONENT_TYPE,_GUID const *,_GUID const *,ushort * const,ushort * const,ulong,ulong,ushort * const,ulong,void * const)
0x180007334  mov     ebx, eax
0x180007336  mov     rcx, cs:WPP_GLOBAL_Control
0x18000733d  lea     rax, WPP_GLOBAL_Control
0x180007344  cmp     rcx, rax
0x180007347  jz      short loc_180007367
0x180007349  test    byte ptr [rcx+1Ch], 10h
0x18000734d  jz      short loc_180007367
0x18000734f  mov     rcx, [rcx+10h]
0x180007353  lea     r8, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids
0x18000735a  mov     edx, 0Ch
0x18000735f  mov     r9d, ebx
0x180007362  call    WPP_SF_D
0x180007367  mov     rsi, [rsp+68h+arg_8]
0x18000736c  mov     eax, ebx
0x18000736e  mov     rbx, [rsp+68h+arg_0]
0x180007373  add     rsp, 60h
0x180007377  pop     rdi
0x180007378  retn
```
