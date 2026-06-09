# SecMgrRemovePortFromList(MSMSEC_PORT_CONTEXT *)

- ea: `0x180013728`
- end: `0x180013949`
- name: `?SecMgrRemovePortFromList@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `545`
- prototype: `void __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180013600`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180013728`
- `0x1800169c0`
- `0x18003445c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800137fc`
- `MobileNetworking!ReleaseWriteLock` at `0x1800137fc`
- `MobileNetworking!AcquireWriteLock` at `0x180013784`
- `MobileNetworking!AcquireWriteLock` at `0x180013784`

## string_xrefs

- `0x180013770`: `SecMgrRemovePortFromList`
- `0x1800137e8`: `SecMgrRemovePortFromList`

## pseudocode

```c
void __fastcall SecMgrRemovePortFromList(struct MSMSEC_PORT_CONTEXT *a1)
{
  __int64 v2; // rax
  struct MSMSEC_PORT_CONTEXT **v3; // rcx
  char *v4; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrRemovePortFromList", 390);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    v4 = (char *)*((_QWORD *)a1 + 3);
    WPP_SF_LDDDDDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      (unsigned __int8)v4[2365],
      (unsigned __int8)v4[2364],
      *((_DWORD *)a1 + 78),
      *((_BYTE *)a1 + 302),
      *((_BYTE *)a1 + 303),
      *((_BYTE *)a1 + 304),
      *((_BYTE *)a1 + 305),
      *((_BYTE *)a1 + 306),
      *((_BYTE *)a1 + 307),
      v4[2360],
      v4[2361],
      v4[2362],
      v4[2363],
      v4[2364],
      v4[2365]);
  }
  v2 = *(_QWORD *)a1;
  if ( *(struct MSMSEC_PORT_CONTEXT **)(*(_QWORD *)a1 + 8LL) != a1
    || (v3 = (struct MSMSEC_PORT_CONTEXT **)*((_QWORD *)a1 + 1), *v3 != a1) )
  {
    __fastfail(3u);
  }
  *v3 = (struct MSMSEC_PORT_CONTEXT *)v2;
  *(_QWORD *)(v2 + 8) = v3;
  *((_QWORD *)a1 + 1) = a1;
  *(_QWORD *)a1 = a1;
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrRemovePortFromList", 415);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, 0);
}

```

## disassembly

```asm
0x180013728  push    rbx
0x18001372a  push    rbp
0x18001372b  push    rsi
0x18001372c  push    rdi
0x18001372d  push    r12
0x18001372f  push    r14
0x180013731  push    r15
0x180013733  sub     rsp, 80h
0x18001373a  mov     r12, rcx
0x18001373d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013744  lea     rbx, WPP_GLOBAL_Control
0x18001374b  cmp     rcx, rbx
0x18001374e  jnz     loc_1800138F1
0x180013754  mov     rcx, [r12+18h]
0x180013759  lea     rdx, aLocking; ">>> Locking >>>"
0x180013760  mov     ecx, [rcx+9C0h]; unsigned int
0x180013766  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18001376b  mov     rcx, [r12+18h]
0x180013770  lea     r8, aSecmgrremovepo; "SecMgrRemovePortFromList"
0x180013777  mov     r9d, 186h
0x18001377d  lea     rdx, [rcx+9D0h]
0x180013784  call    cs:__imp_AcquireWriteLock
0x18001378b  nop     dword ptr [rax+rax+00h]
0x180013790  mov     rcx, cs:WPP_GLOBAL_Control
0x180013797  cmp     rcx, rbx
0x18001379a  jnz     loc_18001382B
0x1800137a0  mov     rax, [r12]
0x1800137a4  cmp     [rax+8], r12
0x1800137a8  jnz     loc_180013942
0x1800137ae  mov     rcx, [r12+8]
0x1800137b3  cmp     [rcx], r12
0x1800137b6  jnz     loc_180013942
0x1800137bc  mov     [rcx], rax
0x1800137bf  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800137c6  mov     [rax+8], rcx
0x1800137ca  mov     [r12+8], r12
0x1800137cf  mov     [r12], r12
0x1800137d3  mov     rcx, [r12+18h]
0x1800137d8  mov     ecx, [rcx+9C0h]; unsigned int
0x1800137de  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800137e3  mov     rcx, [r12+18h]
0x1800137e8  lea     r8, aSecmgrremovepo; "SecMgrRemovePortFromList"
0x1800137ef  mov     r9d, 19Fh
0x1800137f5  lea     rdx, [rcx+9D0h]
0x1800137fc  call    cs:__imp_ReleaseWriteLock
0x180013803  nop     dword ptr [rax+rax+00h]
0x180013808  mov     rcx, cs:WPP_GLOBAL_Control
0x18001380f  cmp     rcx, rbx
0x180013812  jnz     loc_180013918
0x180013818  add     rsp, 80h
0x18001381f  pop     r15
0x180013821  pop     r14
0x180013823  pop     r12
0x180013825  pop     rdi
0x180013826  pop     rsi
0x180013827  pop     rbp
0x180013828  pop     rbx
0x180013829  retn
0x18001382b  test    byte ptr [rcx+44h], 2
0x18001382f  jz      loc_1800137A0
0x180013835  mov     rax, [r12+18h]
0x18001383a  movzx   ebx, byte ptr [r12+133h]
0x180013843  movzx   edi, byte ptr [r12+132h]
0x18001384c  movzx   esi, byte ptr [r12+131h]
0x180013855  movzx   r9d, byte ptr [rax+93Bh]
0x18001385d  movzx   edx, byte ptr [rax+93Dh]
0x180013864  movzx   r8d, byte ptr [rax+93Ch]
0x18001386c  movzx   r10d, byte ptr [rax+93Ah]
0x180013874  movzx   r11d, byte ptr [rax+939h]
0x18001387c  movzx   eax, byte ptr [rax+938h]
0x180013883  movzx   ebp, byte ptr [r12+130h]
0x18001388c  movzx   r14d, byte ptr [r12+12Fh]
0x180013895  movzx   r15d, byte ptr [r12+12Eh]
0x18001389e  mov     rcx, [rcx+38h]
0x1800138a2  mov     [rsp+0B8h+var_40], edx
0x1800138a6  mov     [rsp+0B8h+var_48], r8d
0x1800138ab  mov     [rsp+0B8h+var_50], r9d
0x1800138b0  mov     r9d, [r12+138h]
0x1800138b8  mov     [rsp+0B8h+var_58], r10d
0x1800138bd  mov     [rsp+0B8h+var_60], r11d
0x1800138c2  mov     [rsp+0B8h+var_68], eax
0x1800138c6  mov     [rsp+0B8h+var_70], ebx
0x1800138ca  mov     [rsp+0B8h+var_78], edi
0x1800138ce  mov     [rsp+0B8h+var_80], esi
0x1800138d2  mov     [rsp+0B8h+var_88], ebp
0x1800138d6  mov     [rsp+0B8h+var_90], r14d
0x1800138db  mov     [rsp+0B8h+var_98], r15d
0x1800138e0  call    WPP_SF_LDDDDDDDDDDDD
0x1800138e5  lea     rbx, WPP_GLOBAL_Control
0x1800138ec  jmp     loc_1800137A0
0x1800138f1  test    dword ptr [rcx+44h], 100h
0x1800138f8  jz      loc_180013754
0x1800138fe  mov     rcx, [rcx+38h]
0x180013902  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180013909  mov     edx, 26h ; '&'
0x18001390e  call    WPP_SF_
0x180013913  jmp     loc_180013754
0x180013918  test    dword ptr [rcx+44h], 100h
0x18001391f  jz      loc_180013818
0x180013925  mov     rcx, [rcx+38h]
0x180013929  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180013930  mov     edx, 28h ; '('
0x180013935  xor     r9d, r9d
0x180013938  call    WPP_SF_d
0x18001393d  jmp     loc_180013818
0x180013942  mov     ecx, 3
0x180013947  int     29h; Win8: RtlFailFast(ecx)
```
