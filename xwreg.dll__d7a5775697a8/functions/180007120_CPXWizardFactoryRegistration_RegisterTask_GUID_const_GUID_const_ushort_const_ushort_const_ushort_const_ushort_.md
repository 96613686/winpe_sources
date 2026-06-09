# CPXWizardFactoryRegistration::RegisterTask(_GUID const *,_GUID const *,ushort * const,ushort * const,ushort * const,ushort * const,ulong,unsigned __int64)

- ea: `0x180007120`
- end: `0x180007238`
- name: `?RegisterTask@CPXWizardFactoryRegistration@@UEAAJPEBU_GUID@@0QEAG111K_K@Z`
- size: `280`
- prototype: `__int64 __fastcall(CPXWizardFactoryRegistration *__hidden this, const struct _GUID *, const struct _GUID *, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007120`
- `0x180007820`
- `0x18000bac8`

## pseudocode

```c
__int64 __fastcall CPXWizardFactoryRegistration::RegisterTask(
        CPXWizardFactoryRegistration *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        unsigned __int16 *const a4,
        BYTE *a5,
        BYTE *a6,
        BYTE *a7,
        DWORD a8,
        void *a9)
{
  BYTE *v9; // r11
  BYTE *v11; // rcx
  BYTE *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ebx

  v9 = a7;
  if ( a7 && !*(_WORD *)a7 )
    v9 = 0;
  v11 = a6;
  if ( a6 && !*(_WORD *)a6 )
    v11 = 0;
  v12 = a5;
  if ( a5 && !*(_WORD *)a5 )
    v12 = 0;
  if ( a4 && !*a4 )
    a4 = 0;
  if ( a3 )
  {
    v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v13 )
      a3 = 0;
  }
  if ( a2 )
  {
    v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v14 )
      a2 = 0;
  }
  v15 = HrRegisterWizardFactoryComponent(a2, 2, a3, a4, v12, v11, v9, a8, a9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180007120  mov     [rsp+arg_0], rbx
0x180007125  push    rsi
0x180007126  sub     rsp, 50h
0x18000712a  mov     r11, [rsp+58h+arg_30]
0x180007132  xor     esi, esi
0x180007134  mov     r10, rdx
0x180007137  test    r11, r11
0x18000713a  jz      short loc_180007145
0x18000713c  cmp     [r11], si
0x180007140  jnz     short loc_180007145
0x180007142  mov     r11d, esi
0x180007145  mov     rcx, [rsp+58h+arg_28]
0x18000714d  test    rcx, rcx
0x180007150  jz      short loc_18000715A
0x180007152  cmp     [rcx], si
0x180007155  jnz     short loc_18000715A
0x180007157  mov     rcx, rsi
0x18000715a  mov     rdx, [rsp+58h+arg_20]
0x180007162  test    rdx, rdx
0x180007165  jz      short loc_18000716F
0x180007167  cmp     [rdx], si
0x18000716a  jnz     short loc_18000716F
0x18000716c  mov     rdx, rsi
0x18000716f  test    r9, r9
0x180007172  jz      short loc_18000717D
0x180007174  cmp     [r9], si
0x180007178  jnz     short loc_18000717D
0x18000717a  mov     r9, rsi
0x18000717d  mov     rbx, qword ptr cs:GUID_NULL.Data1
0x180007184  test    r8, r8
0x180007187  jz      short loc_1800071A4
0x180007189  mov     rax, [r8]
0x18000718c  sub     rax, rbx
0x18000718f  jnz     short loc_18000719C
0x180007191  mov     rax, [r8+8]
0x180007195  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000719c  test    rax, rax
0x18000719f  jnz     short loc_1800071A4
0x1800071a1  mov     r8, rsi
0x1800071a4  test    r10, r10
0x1800071a7  jz      short loc_1800071C4
0x1800071a9  mov     rax, [r10]
0x1800071ac  sub     rax, rbx
0x1800071af  jnz     short loc_1800071BC
0x1800071b1  mov     rax, [r10+8]
0x1800071b5  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800071bc  test    rax, rax
0x1800071bf  jnz     short loc_1800071C4
0x1800071c1  mov     r10, rsi
0x1800071c4  mov     rax, [rsp+58h+arg_40]
0x1800071cc  mov     [rsp+58h+var_18], rax
0x1800071d1  mov     eax, [rsp+58h+arg_38]
0x1800071d8  mov     [rsp+58h+var_20], eax
0x1800071dc  mov     [rsp+58h+var_28], r11
0x1800071e1  mov     [rsp+58h+var_30], rcx
0x1800071e6  mov     rcx, r10
0x1800071e9  mov     [rsp+58h+var_38], rdx
0x1800071ee  mov     edx, 2
0x1800071f3  call    ?HrRegisterWizardFactoryComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@0PEBG222KQEAX@Z; HrRegisterWizardFactoryComponent(_GUID const *,tagXW_COMPONENT_TYPE,_GUID const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void * const)
0x1800071f8  mov     ebx, eax
0x1800071fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007201  lea     rax, WPP_GLOBAL_Control
0x180007208  cmp     rcx, rax
0x18000720b  jz      short loc_18000722B
0x18000720d  test    byte ptr [rcx+1Ch], 10h
0x180007211  jz      short loc_18000722B
0x180007213  mov     rcx, [rcx+10h]
0x180007217  lea     r8, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids
0x18000721e  mov     edx, 14h
0x180007223  mov     r9d, ebx
0x180007226  call    WPP_SF_D
0x18000722b  mov     eax, ebx
0x18000722d  mov     rbx, [rsp+58h+arg_0]
0x180007232  add     rsp, 50h
0x180007236  pop     rsi
0x180007237  retn
```
