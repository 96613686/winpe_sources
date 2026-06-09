# InpFillAndProcessQueue

- ea: `0x1400022c0`
- end: `0x140002407`
- name: `InpFillAndProcessQueue`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x140007800`
- `0x140008ac0`

## callees

- `0x1400022c0`
- `0x140002410`
- `0x1400026f0`
- `0x140008ef0`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall InpFillAndProcessQueue(__int64 *a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int v4; // ebp
  unsigned __int8 v5; // r14
  unsigned int v7; // esi
  __int64 v8; // rcx
  void (__fastcall *v9)(_QWORD, _QWORD); // rax
  __int64 result; // rax
  unsigned int v11; // eax
  int v12; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v13; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  v12 = 0;
  v4 = a3;
  v13 = 0;
  *((_BYTE *)a1 + 1408) = (_BYTE)a2 == 2;
  v5 = a2;
  while ( v3 < v4 )
  {
    if ( a1[152] )
    {
      v7 = 7;
      goto LABEL_5;
    }
    if ( (__int64 *)a1[160] == a1 + 160 )
    {
      v7 = InpFillQueue(a1, a2, &v13);
      if ( v7 != 1 )
        goto LABEL_5;
    }
    if ( *((_BYTE *)a1 + 1201) && v5 )
      break;
    v11 = InpProcessQueue(a1, v5, v4 - v3, &v12);
    v3 += v12;
    v7 = v11;
    if ( v11 != 1 )
      goto LABEL_5;
  }
  v7 = 1;
LABEL_5:
  if ( v3 )
  {
    v8 = *a1;
    v9 = *(void (__fastcall **)(_QWORD, _QWORD))(*a1 + 2008);
    if ( *(_BYTE *)(*a1 + 1992) )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD))v9)(v8, *(_QWORD *)(v8 + 2016), v3);
    else
      v9(v8, v3);
  }
  if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 1) != 0 )
    McTemplateK0jjqqh_EtwWriteTransfer(*a1 + 2752, a2, a3, *a1 + 2768, *a1 + 2752, v3, v4, *(_WORD *)(*a1 + 3280));
  result = v7;
  *((_BYTE *)a1 + 1408) = 0;
  return result;
}

```

## disassembly

```asm
0x1400022c0  push    rbx
0x1400022c2  push    rbp
0x1400022c3  push    rdi
0x1400022c4  sub     rsp, 40h
0x1400022c8  xor     edi, edi
0x1400022ca  mov     [rsp+58h+arg_18], r14
0x1400022cf  cmp     dl, 2
0x1400022d2  mov     [rsp+58h+arg_8], edi
0x1400022d6  mov     ebp, r8d
0x1400022d9  mov     [rsp+58h+arg_10], edi
0x1400022dd  setz    al
0x1400022e0  mov     [rsp+58h+arg_0], rsi
0x1400022e5  mov     [rcx+580h], al
0x1400022eb  movzx   r14d, dl
0x1400022ef  mov     rbx, rcx
0x1400022f2  cmp     edi, ebp
0x1400022f4  jnb     loc_1400023AE
0x1400022fa  cmp     qword ptr [rbx+4C0h], 0
0x140002302  jz      short loc_140002354
0x140002304  mov     esi, 7
0x140002309  mov     r14, [rsp+58h+arg_18]
0x14000230e  test    edi, edi
0x140002310  jz      short loc_140002330
0x140002312  mov     rcx, [rbx]
0x140002315  cmp     byte ptr [rcx+7C8h], 0
0x14000231c  mov     rax, [rcx+7D8h]
0x140002323  jnz     loc_1400023BF
0x140002329  mov     edx, edi
0x14000232b  call    _guard_dispatch_icall
0x140002330  test    cs:Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits, 1
0x140002337  jnz     loc_1400023D3
0x14000233d  mov     eax, esi
0x14000233f  mov     byte ptr [rbx+580h], 0
0x140002346  mov     rsi, [rsp+58h+arg_0]
0x14000234b  add     rsp, 40h
0x14000234f  pop     rdi
0x140002350  pop     rbp
0x140002351  pop     rbx
0x140002352  retn
0x140002354  lea     rax, [rbx+500h]
0x14000235b  cmp     [rax], rax
0x14000235e  jz      short loc_140002394
0x140002360  cmp     byte ptr [rbx+4B1h], 0
0x140002367  jnz     short loc_1400023B8
0x140002369  mov     r8d, ebp
0x14000236c  lea     r9, [rsp+58h+arg_8]
0x140002371  sub     r8d, edi
0x140002374  movzx   edx, r14b
0x140002378  mov     rcx, rbx
0x14000237b  call    InpProcessQueue
0x140002380  add     edi, [rsp+58h+arg_8]
0x140002384  mov     esi, eax
0x140002386  cmp     eax, 1
0x140002389  jnz     loc_140002309
0x14000238f  jmp     loc_1400022F2
0x140002394  lea     r8, [rsp+58h+arg_10]
0x140002399  mov     rcx, rbx
0x14000239c  call    InpFillQueue
0x1400023a1  mov     esi, eax
0x1400023a3  cmp     eax, 1
0x1400023a6  jnz     loc_140002309
0x1400023ac  jmp     short loc_140002360
0x1400023ae  mov     esi, 1
0x1400023b3  jmp     loc_140002309
0x1400023b8  test    r14b, r14b
0x1400023bb  jnz     short loc_1400023AE
0x1400023bd  jmp     short loc_140002369
0x1400023bf  mov     rdx, [rcx+7E0h]
0x1400023c6  mov     r8d, edi
0x1400023c9  call    _guard_dispatch_icall
0x1400023ce  jmp     loc_140002330
0x1400023d3  mov     rax, [rbx]
0x1400023d6  lea     rcx, [rax+0AC0h]
0x1400023dd  lea     r9, [rax+0AD0h]
0x1400023e4  movzx   eax, word ptr [rax+0CD0h]
0x1400023eb  mov     [rsp+58h+var_20], ax
0x1400023f0  mov     [rsp+58h+var_28], ebp
0x1400023f4  mov     [rsp+58h+var_30], edi
0x1400023f8  mov     [rsp+58h+var_38], rcx
0x1400023fd  call    McTemplateK0jjqqh_EtwWriteTransfer
0x140002402  jmp     loc_14000233D
```
