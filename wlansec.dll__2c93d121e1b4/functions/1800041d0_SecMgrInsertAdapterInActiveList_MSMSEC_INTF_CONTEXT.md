# SecMgrInsertAdapterInActiveList(MSMSEC_INTF_CONTEXT *)

- ea: `0x1800041d0`
- end: `0x180004314`
- name: `?SecMgrInsertAdapterInActiveList@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `324`
- prototype: `void __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003e80`

## callees

- `0x1800041d0`
- `0x180004518`
- `0x18000892c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180004308`
- `MobileNetworking!AcquireWriteLock` at `0x18000420f`
- `MobileNetworking!AcquireWriteLock` at `0x18000420f`

## pseudocode

```c
void __fastcall SecMgrInsertAdapterInActiveList(struct MSMSEC_INTF_CONTEXT *a1)
{
  _QWORD *v2; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  AcquireWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrInsertAdapterInActiveList", 414);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    WPP_SF_qDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      23,
      *((unsigned __int8 *)a1 + 2364),
      a1,
      *((unsigned __int8 *)a1 + 2360),
      *((unsigned __int8 *)a1 + 2361),
      *((unsigned __int8 *)a1 + 2362),
      *((unsigned __int8 *)a1 + 2363),
      *((unsigned __int8 *)a1 + 2364),
      *((unsigned __int8 *)a1 + 2365));
  v2 = (_QWORD *)qword_1800AF030;
  if ( *(__int64 **)qword_1800AF030 != &qword_1800AF028 )
    __fastfail(3u);
  *(_QWORD *)a1 = &qword_1800AF028;
  *((_QWORD *)a1 + 1) = v2;
  *v2 = a1;
  qword_1800AF030 = (__int64)a1;
  ReleaseWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrInsertAdapterInActiveList", 429);
}

```

## disassembly

```asm
0x1800041d0  mov     [rsp+arg_0], rbx
0x1800041d5  push    rdi
0x1800041d6  sub     rsp, 50h
0x1800041da  mov     rdi, rcx
0x1800041dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041e4  lea     rbx, WPP_GLOBAL_Control
0x1800041eb  cmp     rcx, rbx
0x1800041ee  jnz     loc_1800042AB
0x1800041f4  mov     r9d, 19Eh
0x1800041fa  lea     r8, aSecmgrinsertad; "SecMgrInsertAdapterInActiveList"
0x180004201  lea     rdx, qword_1800AEFC0
0x180004208  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x18000420f  call    cs:__imp_AcquireWriteLock
0x180004216  nop     dword ptr [rax+rax+00h]
0x18000421b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004222  cmp     rcx, rbx
0x180004225  jnz     short loc_180004245
0x180004227  mov     rax, cs:qword_1800AF030
0x18000422e  lea     rcx, qword_1800AF028
0x180004235  cmp     [rax], rcx
0x180004238  jz      loc_1800042D2
0x18000423e  mov     ecx, 3
0x180004243  int     29h; Win8: RtlFailFast(ecx)
0x180004245  test    byte ptr [rcx+44h], 2
0x180004249  jz      short loc_180004227
0x18000424b  movzx   r9d, byte ptr [rdi+93Bh]
0x180004253  mov     edx, 17h
0x180004258  movzx   eax, byte ptr [rdi+93Dh]
0x18000425f  movzx   r8d, byte ptr [rdi+93Ch]
0x180004267  movzx   r10d, byte ptr [rdi+93Ah]
0x18000426f  movzx   r11d, byte ptr [rdi+939h]
0x180004277  movzx   ebx, byte ptr [rdi+938h]
0x18000427e  mov     rcx, [rcx+38h]
0x180004282  mov     [rsp+58h+var_10], eax
0x180004286  mov     [rsp+58h+var_18], r8d
0x18000428b  mov     [rsp+58h+var_20], r9d
0x180004290  mov     r9, rdi
0x180004293  mov     [rsp+58h+var_28], r10d
0x180004298  mov     [rsp+58h+var_30], r11d
0x18000429d  mov     [rsp+58h+var_38], ebx
0x1800042a1  call    WPP_SF_qDDDDDD
0x1800042a6  jmp     loc_180004227
0x1800042ab  test    dword ptr [rcx+44h], 100h
0x1800042b2  jz      loc_1800041F4
0x1800042b8  mov     rcx, [rcx+38h]
0x1800042bc  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800042c3  mov     edx, 16h
0x1800042c8  call    WPP_SF_
0x1800042cd  jmp     loc_1800041F4
0x1800042d2  mov     [rdi], rcx
0x1800042d5  lea     r8, aSecmgrinsertad; "SecMgrInsertAdapterInActiveList"
0x1800042dc  mov     [rdi+8], rax
0x1800042e0  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x1800042e7  mov     [rax], rdi
0x1800042ea  lea     rdx, qword_1800AEFC0
0x1800042f1  mov     r9d, 1ADh
0x1800042f7  mov     cs:qword_1800AF030, rdi
0x1800042fe  mov     rbx, [rsp+58h+arg_0]
0x180004303  add     rsp, 50h
0x180004307  pop     rdi
0x180004308  jmp     cs:__imp_ReleaseWriteLock
```
