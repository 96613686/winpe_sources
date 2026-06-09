# SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)

- ea: `0x1800125b0`
- end: `0x180012965`
- name: `?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `949`
- prototype: `unsigned int __fastcall(void *, struct MSMSEC_INTF_CONTEXT **)`
- caller_count: `23`
- callee_count: `7`
- tags: ``

## callers

- `0x180012df0`
- `0x1800141d0`
- `0x180014d24`
- `0x180015600`
- `0x180017cf0`
- `0x18002a638`
- `0x180030690`
- `0x180030cb0`
- `0x180035ed0`
- `0x1800363c0`
- `0x180038518`
- `0x180039810`
- `0x18003c910`
- `0x180052140`
- `0x1800524f0`
- `0x180052fa0`
- `0x1800536d0`
- `0x180053c30`
- `0x1800540d0`
- `0x180054870`
- `0x180054f40`
- `0x1800552e0`
- `0x18006a6a4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800125b0`
- `0x180012a20`
- `0x180013bc0`
- `0x1800169c0`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800127a5`
- `MobileNetworking!ReleaseWriteLock` at `0x1800127a5`
- `MobileNetworking!AcquireWriteLock` at `0x1800126b4`
- `MobileNetworking!AcquireWriteLock` at `0x1800126b4`

## string_xrefs

- `0x1800126a3`: `SecMgrLockAndCheckAdapterDeleted`
- `0x180012794`: `SecMgrLockAndCheckAdapterDeleted`

## pseudocode

```c
__int64 __fastcall SecMgrValidateRefAndLockAdapter(void ***a1, struct MSMSEC_INTF_CONTEXT **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  unsigned int v7; // eax
  int v8; // r8d
  unsigned int *v9; // rsi
  int v10; // r8d
  PVOID *v11; // rcx
  struct MSMSEC_INTF_CONTEXT *v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && !*a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
      WPP_SF_(v4[7], 25, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    v7 = SecMgrValidateAndDeleteOrRefAdapter(a1, 0, 1, (void ****)&v12);
    v5 = v7;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v7);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 )
    {
      if ( v4 == &WPP_GLOBAL_Control )
        return v5;
      if ( (*((_BYTE *)v4 + 68) & 1) == 0 )
        goto LABEL_32;
      WPP_SF_d(v4[7], 33, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
      goto LABEL_31;
    }
    v9 = (unsigned int *)v12;
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v4[7], 27, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 )
    {
      if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
        WPP_SF_Ls((unsigned int)v4[7], 11, v8, v9[624], (__int64)">>> Locking >>>");
      AcquireWriteLock(v9, v9 + 628, "SecMgrLockAndCheckAdapterDeleted", 482);
      if ( v9[654] )
      {
        v5 = 6;
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
            v11 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
            WPP_SF_Ls((unsigned int)v11[7], 11, v10, v9[624], (__int64)"<<< Unlocking <<<");
        }
        ReleaseWriteLock(v9, v9 + 628, "SecMgrLockAndCheckAdapterDeleted", 496);
      }
      else
      {
        v5 = 0;
      }
    }
    else
    {
      v5 = 87;
      if ( v4 == &WPP_GLOBAL_Control )
      {
LABEL_29:
        if ( v5 )
        {
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
            WPP_SF_d(v4[7], 34, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
          TraceAdapterId(v9[624], "<<< Derefing <<<");
          SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v9, "SecMgrValidateRefAndLockAdapter", 535);
        }
        else
        {
          *a2 = (struct MSMSEC_INTF_CONTEXT *)v9;
        }
        goto LABEL_31;
      }
      if ( (*((_BYTE *)v4 + 68) & 1) == 0 )
      {
LABEL_26:
        if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
        {
          WPP_SF_d(v4[7], 30, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_29;
      }
      WPP_SF_(v4[7], 28, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v5 = 87;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 32, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
LABEL_31:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 35, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800125b0  push    rbx
0x1800125b2  push    rdi
0x1800125b3  push    r14
0x1800125b5  sub     rsp, 30h
0x1800125b9  mov     rdi, rdx
0x1800125bc  mov     [rsp+48h+arg_0], 0
0x1800125c5  mov     rbx, rcx
0x1800125c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125cf  lea     r14, WPP_GLOBAL_Control
0x1800125d6  cmp     rcx, r14
0x1800125d9  jz      short loc_1800125E8
0x1800125db  test    dword ptr [rcx+44h], 100h
0x1800125e2  jnz     loc_1800127B6
0x1800125e8  mov     [rsp+48h+arg_10], rsi
0x1800125ed  test    rbx, rbx
0x1800125f0  jnz     short loc_180012611
0x1800125f2  mov     ebx, 57h ; 'W'
0x1800125f7  cmp     rcx, r14
0x1800125fa  jnz     loc_180012941
0x180012600  mov     rsi, [rsp+48h+arg_10]
0x180012605  mov     eax, ebx
0x180012607  add     rsp, 30h
0x18001260b  pop     r14
0x18001260d  pop     rdi
0x18001260e  pop     rbx
0x18001260f  retn
0x180012611  test    rdi, rdi
0x180012614  jz      short loc_1800125F2
0x180012616  cmp     qword ptr [rdi], 0
0x18001261a  jnz     short loc_1800125F2
0x18001261c  cmp     rcx, r14
0x18001261f  jz      short loc_18001262E
0x180012621  test    dword ptr [rcx+44h], 100h
0x180012628  jnz     loc_1800127D7
0x18001262e  lea     r9, [rsp+48h+arg_0]; struct MSMSEC_INTF_CONTEXT **
0x180012633  xor     edx, edx; int
0x180012635  mov     r8d, 1; int
0x18001263b  mov     rcx, rbx; void *
0x18001263e  call    ?SecMgrValidateAndDeleteOrRefAdapter@@YAKPEAXHHPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateAndDeleteOrRefAdapter(void *,int,int,MSMSEC_INTF_CONTEXT * *)
0x180012643  mov     ebx, eax
0x180012645  mov     rcx, cs:WPP_GLOBAL_Control
0x18001264c  cmp     rcx, r14
0x18001264f  jz      short loc_18001265E
0x180012651  test    dword ptr [rcx+44h], 100h
0x180012658  jnz     loc_1800127F1
0x18001265e  test    ebx, ebx
0x180012660  jnz     loc_180012815
0x180012666  mov     rsi, [rsp+48h+arg_0]
0x18001266b  cmp     rcx, r14
0x18001266e  jz      short loc_18001267D
0x180012670  test    dword ptr [rcx+44h], 100h
0x180012677  jnz     loc_180012845
0x18001267d  test    rsi, rsi
0x180012680  jz      loc_18001272E
0x180012686  mov     [rsp+48h+arg_8], rbp
0x18001268b  cmp     rcx, r14
0x18001268e  jz      short loc_18001269D
0x180012690  test    dword ptr [rcx+44h], 100h
0x180012697  jnz     loc_180012866
0x18001269d  mov     r9d, 1E2h
0x1800126a3  lea     r8, aSecmgrlockandc; "SecMgrLockAndCheckAdapterDeleted"
0x1800126aa  lea     rdx, [rsi+9D0h]
0x1800126b1  mov     rcx, rsi
0x1800126b4  call    cs:__imp_AcquireWriteLock
0x1800126bb  nop     dword ptr [rax+rax+00h]
0x1800126c0  cmp     dword ptr [rsi+0A38h], 0
0x1800126c7  jnz     loc_18001288C
0x1800126cd  xor     ebx, ebx
0x1800126cf  mov     rbp, [rsp+48h+arg_8]
0x1800126d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126db  cmp     rcx, r14
0x1800126de  jz      short loc_1800126E9
0x1800126e0  test    dword ptr [rcx+44h], 100h
0x1800126e7  jnz     short loc_180012758
0x1800126e9  test    ebx, ebx
0x1800126eb  jnz     loc_1800128F2
0x1800126f1  mov     [rdi], rsi
0x1800126f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126fb  cmp     rcx, r14
0x1800126fe  jz      loc_180012600
0x180012704  test    dword ptr [rcx+44h], 100h
0x18001270b  jz      loc_180012600
0x180012711  mov     rcx, [rcx+38h]
0x180012715  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001271c  mov     edx, 23h ; '#'
0x180012721  mov     r9d, ebx
0x180012724  call    WPP_SF_d
0x180012729  jmp     loc_180012600
0x18001272e  mov     ebx, 57h ; 'W'
0x180012733  cmp     rcx, r14
0x180012736  jz      short loc_1800126E9
0x180012738  test    byte ptr [rcx+44h], 1
0x18001273c  jz      short loc_1800126DB
0x18001273e  mov     rcx, [rcx+38h]
0x180012742  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012749  mov     edx, 1Ch
0x18001274e  call    WPP_SF_
0x180012753  jmp     loc_1800126D4
0x180012758  mov     rcx, [rcx+38h]
0x18001275c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012763  mov     edx, 1Eh
0x180012768  mov     r9d, ebx
0x18001276b  call    WPP_SF_d
0x180012770  mov     rcx, cs:WPP_GLOBAL_Control
0x180012777  jmp     loc_1800126E9
0x18001277c  cmp     rcx, r14
0x18001277f  jz      short loc_18001278E
0x180012781  test    dword ptr [rcx+44h], 100h
0x180012788  jnz     loc_1800128CC
0x18001278e  mov     r9d, 1F0h
0x180012794  lea     r8, aSecmgrlockandc; "SecMgrLockAndCheckAdapterDeleted"
0x18001279b  lea     rdx, [rsi+9D0h]
0x1800127a2  mov     rcx, rsi
0x1800127a5  call    cs:__imp_ReleaseWriteLock
0x1800127ac  nop     dword ptr [rax+rax+00h]
0x1800127b1  jmp     loc_1800126CF
0x1800127b6  mov     rcx, [rcx+38h]
0x1800127ba  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800127c1  mov     edx, 1Fh
0x1800127c6  call    WPP_SF_
0x1800127cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127d2  jmp     loc_1800125E8
0x1800127d7  mov     rcx, [rcx+38h]
0x1800127db  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800127e2  mov     edx, 19h
0x1800127e7  call    WPP_SF_
0x1800127ec  jmp     loc_18001262E
0x1800127f1  mov     rcx, [rcx+38h]
0x1800127f5  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800127fc  mov     edx, 1Ah
0x180012801  mov     r9d, ebx
0x180012804  call    WPP_SF_d
0x180012809  mov     rcx, cs:WPP_GLOBAL_Control
0x180012810  jmp     loc_18001265E
0x180012815  cmp     rcx, r14
0x180012818  jz      loc_180012600
0x18001281e  test    byte ptr [rcx+44h], 1
0x180012822  jz      loc_1800126FB
0x180012828  mov     rcx, [rcx+38h]
0x18001282c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012833  mov     edx, 21h ; '!'
0x180012838  mov     r9d, ebx
0x18001283b  call    WPP_SF_d
0x180012840  jmp     loc_1800126F4
0x180012845  mov     rcx, [rcx+38h]
0x180012849  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012850  mov     edx, 1Bh
0x180012855  call    WPP_SF_
0x18001285a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012861  jmp     loc_18001267D
0x180012866  mov     r9d, [rsi+9C0h]
0x18001286d  lea     rax, aLocking; ">>> Locking >>>"
0x180012874  mov     rcx, [rcx+38h]
0x180012878  mov     edx, 0Bh
0x18001287d  mov     [rsp+48h+var_28], rax
0x180012882  call    WPP_SF_Ls
0x180012887  jmp     loc_18001269D
0x18001288c  mov     ebx, 6
0x180012891  mov     rcx, cs:WPP_GLOBAL_Control
0x180012898  cmp     rcx, r14
0x18001289b  jz      loc_18001278E
0x1800128a1  test    byte ptr [rcx+44h], 1
0x1800128a5  jz      loc_18001277C
0x1800128ab  mov     rcx, [rcx+38h]
0x1800128af  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800128b6  mov     edx, 1Dh
0x1800128bb  call    WPP_SF_
0x1800128c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128c7  jmp     loc_18001277C
0x1800128cc  mov     r9d, [rsi+9C0h]
0x1800128d3  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x1800128da  mov     rcx, [rcx+38h]
0x1800128de  mov     edx, 0Bh
0x1800128e3  mov     [rsp+48h+var_28], rax
0x1800128e8  call    WPP_SF_Ls
0x1800128ed  jmp     loc_18001278E
0x1800128f2  cmp     rcx, r14
0x1800128f5  jz      short loc_180012915
0x1800128f7  test    byte ptr [rcx+44h], 1
0x1800128fb  jz      short loc_180012915
0x1800128fd  mov     rcx, [rcx+38h]
0x180012901  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012908  mov     edx, 22h ; '"'
0x18001290d  mov     r9d, ebx
0x180012910  call    WPP_SF_d
0x180012915  mov     ecx, [rsi+9C0h]; unsigned int
0x18001291b  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180012922  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180012927  mov     r8d, 217h; int
0x18001292d  lea     rdx, aSecmgrvalidate_0; "SecMgrValidateRefAndLockAdapter"
0x180012934  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180012937  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18001293c  jmp     loc_1800126F4
0x180012941  test    byte ptr [rcx+44h], 1
0x180012945  jz      loc_1800126FB
0x18001294b  mov     rcx, [rcx+38h]
0x18001294f  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180012956  mov     edx, 20h ; ' '
0x18001295b  call    WPP_SF_
0x180012960  jmp     loc_1800126F4
```
