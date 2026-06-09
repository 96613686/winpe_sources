# CPXWizardTaskStub::CanHostTask(_GUID * const,ushort)

- ea: `0x180018f80`
- end: `0x1800190f5`
- name: `?CanHostTask@CPXWizardTaskStub@@UEAAJQEAU_GUID@@G@Z`
- size: `373`
- prototype: `__int64 __fastcall(CPXWizardTaskStub *__hidden this, struct _GUID *const, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002556`
- `0x18000ae04`
- `0x18000ae44`
- `0x180018f80`
- `0x18001af64`
- `0x18001b6e4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190b7`

## pseudocode

```c
__int64 __fastcall CPXWizardTaskStub::CanHostTask(CPXWizardTaskStub *this, struct _GUID *const a2, unsigned __int16 a3)
{
  __int64 v4; // rcx
  unsigned int v5; // r14d
  __int64 v6; // rax
  unsigned int v7; // ebx
  int v8; // eax
  _OWORD *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  void *Src; // [rsp+68h] [rbp+38h] BYREF
  void *v15; // [rsp+78h] [rbp+48h] BYREF

  Src = 0;
  v4 = *((_QWORD *)this + 10);
  v5 = a3;
  if ( a2 )
  {
    v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v6 )
      a2 = 0;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, struct _GUID *const, void **))(*(_QWORD *)v4 + 48LL))(v4, a2, &Src);
  if ( !v7 && Src )
  {
    v15 = 0;
    LODWORD(Size) = 0;
    v8 = HrMapMarshalID(v5, &v15, (unsigned int *)&Size);
    v7 = v8;
    if ( v15 )
    {
      memcpy_0(v15, Src, (unsigned int)Size);
      v8 = HrUnmapMarshalID(v15);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v9 = Src;
        v7 = 0;
        *((_OWORD *)this + 12) = *(_OWORD *)Src;
        *((_OWORD *)this + 13) = v9[1];
        *((_OWORD *)this + 14) = v9[2];
        *((_OWORD *)this + 15) = v9[3];
        goto LABEL_18;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v11 = 13;
LABEL_17:
        WPP_SF_DD(v10[2], v11, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids, v5, v8);
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v11 = 14;
        goto LABEL_17;
      }
    }
  }
LABEL_18:
  CoTaskMemFree(Src);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180018f80  push    rbp
0x180018f82  push    rbx
0x180018f83  push    rdi
0x180018f84  push    r12
0x180018f86  push    r14
0x180018f88  mov     rbp, rsp
0x180018f8b  sub     rsp, 30h
0x180018f8f  mov     [rbp+Src], 0
0x180018f97  mov     rdi, rcx
0x180018f9a  mov     rcx, [rcx+50h]
0x180018f9e  movzx   r14d, r8w
0x180018fa2  mov     rax, [rcx]
0x180018fa5  mov     r9, [rax+30h]
0x180018fa9  test    rdx, rdx
0x180018fac  jz      short loc_180018FCC
0x180018fae  mov     rax, [rdx]
0x180018fb1  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180018fb8  jnz     short loc_180018FC5
0x180018fba  mov     rax, [rdx+8]
0x180018fbe  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180018fc5  test    rax, rax
0x180018fc8  jnz     short loc_180018FCC
0x180018fca  xor     edx, edx
0x180018fcc  lea     r8, [rbp+Src]
0x180018fd0  mov     rax, r9
0x180018fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fd8  lea     r12, WPP_GLOBAL_Control
0x180018fdf  mov     ebx, eax
0x180018fe1  test    eax, eax
0x180018fe3  jnz     loc_1800190B3
0x180018fe9  cmp     [rbp+Src], 0
0x180018fee  jz      loc_1800190B3
0x180018ff4  lea     r8, [rbp+Size]; unsigned int *
0x180018ff8  mov     [rbp+arg_18], 0
0x180019000  lea     rdx, [rbp+arg_18]; void **
0x180019004  mov     dword ptr [rbp+Size], eax
0x180019007  movzx   ecx, r14w; unsigned __int16
0x18001900b  call    ?HrMapMarshalID@@YAJGPEAPEAXPEAK@Z; HrMapMarshalID(ushort,void * *,ulong *)
0x180019010  cmp     [rbp+arg_18], 0
0x180019015  mov     ebx, eax
0x180019017  jz      short loc_180019085
0x180019019  mov     r8d, dword ptr [rbp+Size]; Size
0x18001901d  mov     rdx, [rbp+Src]; Src
0x180019021  mov     rcx, [rbp+arg_18]; void *
0x180019025  call    memcpy_0
0x18001902a  mov     rcx, [rbp+arg_18]; void *
0x18001902e  call    ?HrUnmapMarshalID@@YAJPEAX@Z; HrUnmapMarshalID(void *)
0x180019033  mov     ebx, eax
0x180019035  test    eax, eax
0x180019037  js      short loc_18001906C
0x180019039  mov     rax, [rbp+Src]
0x18001903d  xor     ebx, ebx
0x18001903f  movups  xmm0, xmmword ptr [rax]
0x180019042  movups  xmmword ptr [rdi+0C0h], xmm0
0x180019049  movups  xmm1, xmmword ptr [rax+10h]
0x18001904d  movups  xmmword ptr [rdi+0D0h], xmm1
0x180019054  movups  xmm0, xmmword ptr [rax+20h]
0x180019058  movups  xmmword ptr [rdi+0E0h], xmm0
0x18001905f  movups  xmm1, xmmword ptr [rax+30h]
0x180019063  movups  xmmword ptr [rdi+0F0h], xmm1
0x18001906a  jmp     short loc_1800190B3
0x18001906c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019073  cmp     rcx, r12
0x180019076  jz      short loc_1800190B3
0x180019078  test    byte ptr [rcx+1Ch], 4
0x18001907c  jz      short loc_1800190B3
0x18001907e  mov     edx, 0Dh
0x180019083  jmp     short loc_18001909C
0x180019085  mov     rcx, cs:WPP_GLOBAL_Control
0x18001908c  cmp     rcx, r12
0x18001908f  jz      short loc_1800190B3
0x180019091  test    byte ptr [rcx+1Ch], 4
0x180019095  jz      short loc_1800190B3
0x180019097  mov     edx, 0Eh
0x18001909c  mov     rcx, [rcx+10h]
0x1800190a0  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x1800190a7  mov     r9d, r14d
0x1800190aa  mov     [rsp+30h+var_10], eax
0x1800190ae  call    WPP_SF_DD
0x1800190b3  mov     rcx, [rbp+Src]; pv
0x1800190b7  call    cs:__imp_CoTaskMemFree
0x1800190bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190c4  cmp     rcx, r12
0x1800190c7  jz      short loc_1800190E7
0x1800190c9  test    byte ptr [rcx+1Ch], 10h
0x1800190cd  jz      short loc_1800190E7
0x1800190cf  mov     rcx, [rcx+10h]
0x1800190d3  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x1800190da  mov     edx, 0Fh
0x1800190df  mov     r9d, ebx
0x1800190e2  call    WPP_SF_d
0x1800190e7  mov     eax, ebx
0x1800190e9  add     rsp, 30h
0x1800190ed  pop     r14
0x1800190ef  pop     r12
0x1800190f1  pop     rdi
0x1800190f2  pop     rbx
0x1800190f3  pop     rbp
0x1800190f4  retn
```
