# UdfVerifyScbOperation

- ea: `0x140045f10`
- end: `0x140046285`
- name: `UdfVerifyScbOperation`
- size: `885`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010f0`
- `0x14000dc18`
- `0x14000feb4`
- `0x14002d330`
- `0x14002f034`
- `0x140031f84`
- `0x140035794`
- `0x1400362e0`
- `0x140036888`
- `0x1400369d4`
- `0x140036c38`
- `0x140036e50`
- `0x140037070`
- `0x14003f4c8`
- `0x140044950`
- `0x140044f90`
- `0x140047a10`
- `0x140048190`
- `0x140054830`
- `0x140057c30`
- `0x140058470`
- `0x140058630`

## callees

- `0x140045f10`
- `0x14004628c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140046075`
- `ntoskrnl!ExRaiseStatus` at `0x1400460e5`
- `ntoskrnl!ExRaiseStatus` at `0x140046164`
- `ntoskrnl!ExRaiseStatus` at `0x1400461ae`
- `ntoskrnl!ExRaiseStatus` at `0x1400461fc`
- `ntoskrnl!ExRaiseStatus` at `0x14004621c`
- `ntoskrnl!ExRaiseStatus` at `0x14004625a`
- `ntoskrnl!ExRaiseStatus` at `0x140046278`
- `ntoskrnl!ExRaiseStatus` at `0x140046075`
- `ntoskrnl!ExRaiseStatus` at `0x1400460e5`
- `ntoskrnl!ExRaiseStatus` at `0x140046164`
- `ntoskrnl!ExRaiseStatus` at `0x1400461ae`
- `ntoskrnl!ExRaiseStatus` at `0x1400461fc`
- `ntoskrnl!ExRaiseStatus` at `0x14004621c`
- `ntoskrnl!ExRaiseStatus` at `0x14004625a`
- `ntoskrnl!ExRaiseStatus` at `0x140046278`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14004614c`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140046196`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140046242`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14004614c`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140046196`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140046242`

## pseudocode

```c
char __fastcall UdfVerifyScbOperation(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  int v5; // edx
  __int64 v6; // r15
  __int64 v7; // r14
  int v8; // esi
  struct _DEVICE_OBJECT *v9; // r10
  ULONG Flags; // r9d
  __int64 v11; // r12
  char *v12; // rdx
  __int64 v13; // r13
  int v14; // ecx
  char v15; // al
  char v17; // r8
  NTSTATUS v18; // eax
  int v19; // ecx
  bool v20; // zf
  NTSTATUS v21; // ecx
  struct _DEVICE_OBJECT *v22; // [rsp+20h] [rbp-48h]
  char v23; // [rsp+78h] [rbp+10h]
  char *v24; // [rsp+88h] [rbp+20h]

  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL);
  v5 = *(_DWORD *)(v4 + 48);
  if ( (v5 & 0x20000000) != 0 || (*(_DWORD *)(a2 + 212) & 0x8000000) == 0 )
  {
    v6 = 668;
    v7 = 680;
  }
  else
  {
    v7 = 880;
    v6 = 868;
  }
  v8 = *(_DWORD *)(v4 + 52);
  if ( (unsigned int)(v8 - 3) <= 1 )
  {
    if ( a1 )
    {
      if ( (v5 & 0x1000) != 0 )
      {
        *(_DWORD *)(a1 + 24) = -1073741202;
        ExRaiseStatus(-1073741202);
      }
      *(_DWORD *)(a1 + 24) = -1073741672;
      ExRaiseStatus(-1073741672);
    }
    return 0;
  }
  v9 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v4 + 8) + 16LL);
  v22 = v9;
  Flags = v9->Flags;
  v23 = Flags;
  if ( a1 )
  {
    v11 = *(_QWORD *)(a1 + 8);
    v12 = *(char **)(v11 + 184);
    v24 = v12;
    v13 = *((_QWORD *)v12 + 6);
    if ( v8 == 2 && *(_DWORD *)(a2 + 216) == 1 )
    {
      UdfVerifyScbBranch(a1);
      v12 = v24;
      LOBYTE(Flags) = v23;
      v9 = v22;
    }
    v14 = *(_DWORD *)(a2 + 216);
    if ( (v13 && (*(_DWORD *)(v13 + 80) & 0x4000) != 0 || (*(_DWORD *)(a2 + 212) & 0x200) != 0 || v14 >= 2)
      && ((*(_DWORD *)(v11 + 16) & 2) == 0 || v14) )
    {
      v17 = *v12;
      if ( ((*v12 - 2) & 0xEF) != 0 )
      {
        if ( v17 == 5 )
        {
          if ( v14 )
            goto LABEL_30;
        }
        else if ( (unsigned __int8)(v17 - 3) > 1u || (v12[1] & 4) == 0 )
        {
          if ( !v14 )
          {
            v18 = -1073741528;
            if ( (*(_DWORD *)(a2 + 212) & 0x200) != 0 )
              v18 = -1073741533;
LABEL_32:
            *(_DWORD *)(a1 + 24) = v18;
            ExRaiseStatus(v18);
          }
LABEL_30:
          v18 = -1073741672;
          if ( v14 != 2 )
            v18 = -1073741566;
          goto LABEL_32;
        }
      }
    }
    if ( (*(_DWORD *)(v11 + 16) & 2) == 0 )
    {
      v15 = *v12;
      if ( *v12 != 4 )
      {
        if ( v15 == 6 )
        {
          if ( *((_DWORD *)v12 + 4) == 14 )
            goto LABEL_16;
        }
        else if ( v15 != 13 || v12[1] || *((_DWORD *)v12 + 6) != 590020 )
        {
          goto LABEL_16;
        }
      }
      v19 = *(_DWORD *)(v4 + 48);
      if ( (v19 & 0x80u) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), v9);
        *(_DWORD *)(a1 + 24) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      if ( (v19 & 0x10) != 0 || (*(_DWORD *)(a2 + 212) & 0x8000) != 0 )
      {
        v20 = (v19 & 0x20) == 0;
        v21 = -1073739770;
        if ( v20 )
          v21 = -1073741790;
        *(_DWORD *)(a1 + 24) = v21;
        ExRaiseStatus(v21);
      }
      if ( (*(_DWORD *)(v4 + 84) & 0x10) != 0
        && (*(_DWORD *)(a1 + 28) & 0x20) != 0
        && *(_DWORD *)(v4 + v6) <= *(_DWORD *)(v4 + v7) )
      {
        *(_DWORD *)(a1 + 24) = -1073741697;
        ExRaiseStatus(-1073741697);
      }
    }
  }
LABEL_16:
  if ( (Flags & 2) != 0 )
  {
    if ( !a1 )
      return 0;
    if ( (*(_DWORD *)(a1 + 28) & 0x2000) == 0 )
    {
      IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), v9);
      *(_DWORD *)(a1 + 24) = -2147483626;
      ExRaiseStatus(-2147483626);
    }
  }
  if ( v8 == 2 )
  {
    if ( *(_DWORD *)(a2 + 216) )
      return 0;
  }
  else if ( v8 != 1 )
  {
    if ( !a1 )
      return 0;
    if ( !v8 )
    {
      IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), v9);
      *(_DWORD *)(a1 + 24) = -1073741806;
      ExRaiseStatus(-1073741806);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140045f10  push    rbx
0x140045f12  push    rbp
0x140045f13  push    rsi
0x140045f14  push    rdi
0x140045f15  push    r14
0x140045f17  push    r15
0x140045f19  sub     rsp, 38h
0x140045f1d  mov     rax, [rdx+88h]
0x140045f24  mov     rbx, rdx
0x140045f27  mov     rbp, rcx
0x140045f2a  mov     rdi, [rax+8]
0x140045f2e  mov     edx, [rdi+30h]
0x140045f31  bt      edx, 1Dh
0x140045f35  jnb     loc_140046039
0x140045f3b  mov     r15d, 29Ch
0x140045f41  mov     r14d, 2A8h
0x140045f47  mov     esi, [rdi+34h]
0x140045f4a  mov     [rsp+68h+arg_0], r12
0x140045f4f  mov     [rsp+68h+var_38], r13
0x140045f54  lea     eax, [rsi-3]
0x140045f57  cmp     eax, 1
0x140045f5a  jbe     loc_14004605A
0x140045f60  mov     rax, [rdi+8]
0x140045f64  mov     r10, [rax+10h]
0x140045f68  mov     [rsp+68h+var_48], r10
0x140045f6d  mov     r9d, [r10+30h]
0x140045f71  mov     [rsp+68h+arg_8], r9d
0x140045f76  test    rbp, rbp
0x140045f79  jz      loc_140045FFF
0x140045f7f  mov     r12, [rcx+8]
0x140045f83  mov     rdx, [r12+0B8h]
0x140045f8b  mov     [rsp+68h+arg_18], rdx
0x140045f93  mov     r13, [rdx+30h]
0x140045f97  cmp     esi, 2
0x140045f9a  jnz     short loc_140045FA9
0x140045f9c  cmp     dword ptr [rbx+0D8h], 1
0x140045fa3  jz      loc_140046082
0x140045fa9  mov     ecx, [rbx+0D8h]
0x140045faf  test    r13, r13
0x140045fb2  jz      short loc_140045FC2
0x140045fb4  test    dword ptr [r13+50h], 4000h
0x140045fbc  jnz     loc_1400460A1
0x140045fc2  test    dword ptr [rbx+0D4h], 200h
0x140045fcc  jnz     loc_1400460A1
0x140045fd2  cmp     ecx, 2
0x140045fd5  jge     loc_1400460A1
0x140045fdb  mov     eax, [r12+10h]
0x140045fe0  test    al, 2
0x140045fe2  jnz     short loc_140045FFF
0x140045fe4  movzx   eax, byte ptr [rdx]
0x140045fe7  cmp     al, 4
0x140045fe9  jz      loc_140046188
0x140045fef  cmp     al, 6
0x140045ff1  jz      loc_140046123
0x140045ff7  cmp     al, 0Dh
0x140045ff9  jz      loc_140046171
0x140045fff  test    r9b, 2
0x140046003  jnz     loc_14004612F
0x140046009  cmp     esi, 2
0x14004600c  jnz     loc_140046229
0x140046012  cmp     dword ptr [rbx+0D8h], 0
0x140046019  jz      loc_140046267
0x14004601f  xor     al, al
0x140046021  mov     r13, [rsp+68h+var_38]
0x140046026  mov     r12, [rsp+68h+arg_0]
0x14004602b  add     rsp, 38h
0x14004602f  pop     r15
0x140046031  pop     r14
0x140046033  pop     rdi
0x140046034  pop     rsi
0x140046035  pop     rbp
0x140046036  pop     rbx
0x140046037  retn
0x140046039  test    dword ptr [rbx+0D4h], 8000000h
0x140046043  jz      loc_140045F3B
0x140046049  mov     r14d, 370h
0x14004604f  mov     r15d, 364h
0x140046055  jmp     loc_140045F47
0x14004605a  test    rbp, rbp
0x14004605d  jz      short loc_14004601F
0x14004605f  bt      edx, 0Ch
0x140046063  jnb     loc_14004626E
0x140046069  mov     dword ptr [rcx+18h], 0C000026Eh
0x140046070  mov     ecx, 0C000026Eh; Status
0x140046075  call    cs:__imp_ExRaiseStatus
0x140046082  mov     rdx, rbx
0x140046085  call    UdfVerifyScbBranch
0x14004608a  mov     rdx, [rsp+68h+arg_18]
0x140046092  mov     r9d, [rsp+68h+arg_8]
0x140046097  mov     r10, [rsp+68h+var_48]
0x14004609c  jmp     loc_140045FA9
0x1400460a1  mov     eax, [r12+10h]
0x1400460a6  test    al, 2
0x1400460a8  jz      short loc_1400460B2
0x1400460aa  test    ecx, ecx
0x1400460ac  jz      loc_140045FDB
0x1400460b2  movzx   r8d, byte ptr [rdx]
0x1400460b6  lea     eax, [r8-2]
0x1400460ba  test    al, 0EFh
0x1400460bc  jz      loc_140045FDB
0x1400460c2  cmp     r8b, 5
0x1400460c6  jnz     short loc_1400460F2
0x1400460c8  test    ecx, ecx
0x1400460ca  jz      loc_140045FDB
0x1400460d0  cmp     ecx, 2
0x1400460d3  mov     eax, 0C0000098h
0x1400460d8  mov     edx, 0C0000102h
0x1400460dd  cmovnz  eax, edx
0x1400460e0  mov     ecx, eax; Status
0x1400460e2  mov     [rbp+18h], eax
0x1400460e5  call    cs:__imp_ExRaiseStatus
0x1400460f2  sub     r8b, 3
0x1400460f6  cmp     r8b, 1
0x1400460fa  ja      short loc_140046106
0x1400460fc  test    byte ptr [rdx+1], 4
0x140046100  jnz     loc_140045FDB
0x140046106  test    ecx, ecx
0x140046108  jnz     short loc_1400460D0
0x14004610a  test    dword ptr [rbx+0D4h], 200h
0x140046114  mov     eax, 0C0000128h
0x140046119  mov     ecx, 0C0000123h
0x14004611e  cmovnz  eax, ecx
0x140046121  jmp     short loc_1400460E0
0x140046123  cmp     dword ptr [rdx+10h], 0Eh
0x140046127  jz      loc_140045FFF
0x14004612d  jmp     short loc_140046188
0x14004612f  test    rbp, rbp
0x140046132  jz      loc_14004601F
0x140046138  test    dword ptr [rbp+1Ch], 2000h
0x14004613f  jnz     loc_140046009
0x140046145  mov     rcx, [rbp+8]; Irp
0x140046149  mov     rdx, r10; DeviceObject
0x14004614c  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x140046153  nop     dword ptr [rax+rax+00h]
0x140046158  mov     ecx, 80000016h; Status
0x14004615d  mov     dword ptr [rbp+18h], 80000016h
0x140046164  call    cs:__imp_ExRaiseStatus
0x140046171  cmp     byte ptr [rdx+1], 0
0x140046175  jnz     loc_140045FFF
0x14004617b  cmp     dword ptr [rdx+18h], 900C4h
0x140046182  jnz     loc_140045FFF
0x140046188  mov     ecx, [rdi+30h]
0x14004618b  test    cl, cl
0x14004618d  jns     short loc_1400461BB
0x14004618f  mov     rcx, [rbp+8]; Irp
0x140046193  mov     rdx, r10; DeviceObject
0x140046196  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14004619d  nop     dword ptr [rax+rax+00h]
0x1400461a2  mov     ecx, 0C00000A2h; Status
0x1400461a7  mov     dword ptr [rbp+18h], 0C00000A2h
0x1400461ae  call    cs:__imp_ExRaiseStatus
0x1400461bb  test    cl, 10h
0x1400461be  jnz     short loc_140046209
0x1400461c0  test    dword ptr [rbx+0D4h], 8000h
0x1400461ca  jnz     short loc_140046209
0x1400461cc  mov     eax, [rdi+54h]
0x1400461cf  test    al, 10h
0x1400461d1  jz      loc_140045FFF
0x1400461d7  mov     eax, [rbp+1Ch]
0x1400461da  test    al, 20h
0x1400461dc  jz      loc_140045FFF
0x1400461e2  mov     eax, [rdi+r14]
0x1400461e6  cmp     [rdi+r15], eax
0x1400461ea  ja      loc_140045FFF
0x1400461f0  mov     ecx, 0C000007Fh; Status
0x1400461f5  mov     dword ptr [rbp+18h], 0C000007Fh
0x1400461fc  call    cs:__imp_ExRaiseStatus
0x140046209  test    cl, 20h
0x14004620c  mov     eax, 0C0000022h
0x140046211  mov     ecx, 0C0000806h
0x140046216  cmovz   ecx, eax; Status
0x140046219  mov     [rbp+18h], ecx
0x14004621c  call    cs:__imp_ExRaiseStatus
0x140046229  cmp     esi, 1
0x14004622c  jz      short loc_140046267
0x14004622e  test    rbp, rbp
0x140046231  jz      loc_14004601F
0x140046237  test    esi, esi
0x140046239  jnz     short loc_140046267
0x14004623b  mov     rcx, [rbp+8]; Irp
0x14004623f  mov     rdx, r10; DeviceObject
0x140046242  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x140046249  nop     dword ptr [rax+rax+00h]
0x14004624e  mov     ecx, 0C0000012h; Status
0x140046253  mov     dword ptr [rbp+18h], 0C0000012h
0x14004625a  call    cs:__imp_ExRaiseStatus
0x140046267  mov     al, 1
0x140046269  jmp     loc_140046021
0x14004626e  mov     eax, 0C0000098h
0x140046273  mov     [rcx+18h], eax
0x140046276  mov     ecx, eax; Status
0x140046278  call    cs:__imp_ExRaiseStatus
```
