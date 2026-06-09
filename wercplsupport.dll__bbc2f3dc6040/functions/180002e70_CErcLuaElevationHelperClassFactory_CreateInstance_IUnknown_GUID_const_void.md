# CErcLuaElevationHelperClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002e70`
- end: `0x180002fe2`
- name: `?CreateInstance@CErcLuaElevationHelperClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `370`
- prototype: `__int64 __fastcall(CErcLuaElevationHelperClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001634`
- `0x180002850`
- `0x180002e70`
- `0x180003d98`
- `0x180006c9c`
- `0x1800073d4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CErcLuaElevationHelperClassFactory::CreateInstance(
        CErcLuaElevationHelperClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // edi
  CManagedObj *v7; // rax
  CManagedObj *v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rdx

  *a4 = 0;
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
    v6 = -2147221232;
LABEL_22:
    *a4 = 0;
    return (unsigned int)v6;
  }
  v7 = (CManagedObj *)operator new(0x30u);
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
    v6 = -2147024882;
    goto LABEL_22;
  }
  CManagedObj::CManagedObj(v7);
  *((_DWORD *)v8 + 8) = 0;
  *(_QWORD *)v8 = &CErcLuaElevationHelper::`vftable'{for `CManagedObj'};
  *((_QWORD *)v8 + 5) = 0;
  *((_QWORD *)v8 + 3) = &CErcLuaElevationHelper::`vftable'{for `IErcLUAElevationHelper'};
  v6 = CErcLuaElevationHelper::Init(v8);
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v10 = 12;
    goto LABEL_15;
  }
  v6 = (**(__int64 (__fastcall ***)(CManagedObj *, const struct _GUID *, void **))v8)(v8, a3, a4);
  if ( v6 >= 0 )
    return 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 13;
LABEL_15:
    WPP_SF_d(v9[2], v10, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, (unsigned int)v6);
  }
LABEL_16:
  *a4 = 0;
  (*(void (__fastcall **)(CManagedObj *, __int64))(*(_QWORD *)v8 + 24LL))(v8, 1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002e70  push    rbx
0x180002e72  push    rbp
0x180002e73  push    rsi
0x180002e74  push    rdi
0x180002e75  sub     rsp, 28h
0x180002e79  mov     qword ptr [r9], 0
0x180002e80  mov     rsi, r9
0x180002e83  mov     rbp, r8
0x180002e86  test    rdx, rdx
0x180002e89  jz      short loc_180002EC3
0x180002e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e92  lea     rax, WPP_GLOBAL_Control
0x180002e99  cmp     rcx, rax
0x180002e9c  jz      short loc_180002EB9
0x180002e9e  test    byte ptr [rcx+1Ch], 1
0x180002ea2  jz      short loc_180002EB9
0x180002ea4  mov     rcx, [rcx+10h]
0x180002ea8  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180002eaf  mov     edx, 0Ah
0x180002eb4  call    WPP_SF_
0x180002eb9  mov     edi, 80040110h
0x180002ebe  jmp     loc_180002FD0
0x180002ec3  mov     ecx, 30h ; '0'; Size
0x180002ec8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ecd  mov     rbx, rax
0x180002ed0  test    rax, rax
0x180002ed3  jz      loc_180002F9D
0x180002ed9  mov     rcx, rax; this
0x180002edc  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180002ee1  lea     rax, ??_7CErcLuaElevationHelper@@6BCManagedObj@@@; const CErcLuaElevationHelper::`vftable'{for `CManagedObj'}
0x180002ee8  mov     dword ptr [rbx+20h], 0
0x180002eef  mov     [rbx], rax
0x180002ef2  mov     rcx, rbx; this
0x180002ef5  lea     rax, ??_7CErcLuaElevationHelper@@6BIErcLUAElevationHelper@@@; const CErcLuaElevationHelper::`vftable'{for `IErcLUAElevationHelper'}
0x180002efc  mov     qword ptr [rbx+28h], 0
0x180002f04  mov     [rbx+18h], rax
0x180002f08  call    ?Init@CErcLuaElevationHelper@@QEAAJXZ; CErcLuaElevationHelper::Init(void)
0x180002f0d  mov     edi, eax
0x180002f0f  test    eax, eax
0x180002f11  jns     short loc_180002F33
0x180002f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f1a  lea     rax, WPP_GLOBAL_Control
0x180002f21  cmp     rcx, rax
0x180002f24  jz      short loc_180002F7E
0x180002f26  test    byte ptr [rcx+1Ch], 1
0x180002f2a  jz      short loc_180002F7E
0x180002f2c  mov     edx, 0Ch
0x180002f31  jmp     short loc_180002F6B
0x180002f33  mov     rax, [rbx]
0x180002f36  mov     r8, rsi
0x180002f39  mov     rdx, rbp
0x180002f3c  mov     rcx, rbx
0x180002f3f  mov     rax, [rax]
0x180002f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f47  mov     edi, eax
0x180002f49  test    eax, eax
0x180002f4b  jns     short loc_180002F99
0x180002f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f54  lea     rax, WPP_GLOBAL_Control
0x180002f5b  cmp     rcx, rax
0x180002f5e  jz      short loc_180002F7E
0x180002f60  test    byte ptr [rcx+1Ch], 1
0x180002f64  jz      short loc_180002F7E
0x180002f66  mov     edx, 0Dh
0x180002f6b  mov     rcx, [rcx+10h]
0x180002f6f  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180002f76  mov     r9d, edi
0x180002f79  call    WPP_SF_d
0x180002f7e  xor     eax, eax
0x180002f80  mov     edx, 1
0x180002f85  mov     [rsi], rax
0x180002f88  mov     rcx, rbx
0x180002f8b  mov     rax, [rbx]
0x180002f8e  mov     rax, [rax+18h]
0x180002f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f97  jmp     short loc_180002FD7
0x180002f99  xor     edi, edi
0x180002f9b  jmp     short loc_180002FD7
0x180002f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fa4  lea     rax, WPP_GLOBAL_Control
0x180002fab  cmp     rcx, rax
0x180002fae  jz      short loc_180002FCB
0x180002fb0  test    byte ptr [rcx+1Ch], 1
0x180002fb4  jz      short loc_180002FCB
0x180002fb6  mov     rcx, [rcx+10h]
0x180002fba  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180002fc1  mov     edx, 0Bh
0x180002fc6  call    WPP_SF_
0x180002fcb  mov     edi, 8007000Eh
0x180002fd0  mov     qword ptr [rsi], 0
0x180002fd7  mov     eax, edi
0x180002fd9  add     rsp, 28h
0x180002fdd  pop     rdi
0x180002fde  pop     rsi
0x180002fdf  pop     rbp
0x180002fe0  pop     rbx
0x180002fe1  retn
```
