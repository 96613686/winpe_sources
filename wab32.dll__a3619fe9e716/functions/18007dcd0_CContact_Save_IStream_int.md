# CContact::Save(IStream *,int)

- ea: `0x18007dcd0`
- end: `0x18007de15`
- name: `?Save@CContact@@UEAAJPEAUIStream@@H@Z`
- size: `325`
- prototype: `__int64 __fastcall(CContact *__hidden this, struct IStream *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007de20`

## callees

- `0x180002818`
- `0x18007dcd0`
- `0x18007e9e0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!__imp_IStream_Reset` at `0x18007dd9b`
- `SHLWAPI!__imp_IStream_Reset` at `0x18007dd9b`
- `SHLWAPI!__imp_IStream_Size` at `0x18007dd88`
- `SHLWAPI!__imp_IStream_Size` at `0x18007dd88`
- `KERNEL32!GetCurrentThreadId` at `0x18007dcfd`
- `KERNEL32!GetCurrentThreadId` at `0x18007dcfd`

## pseudocode

```c
__int64 __fastcall CContact::Save(CContact *this, struct IStream *a2, unsigned int a3)
{
  int v3; // ebx
  HRESULT v7; // ebx
  int v8; // eax
  IStream *v9; // rcx
  ULARGE_INTEGER pui; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 170);
  v12 = 0;
  pui.QuadPart = 0;
  if ( GetCurrentThreadId() != v3 )
  {
    v7 = -2147417842;
    goto LABEL_17;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    goto LABEL_17;
  }
  if ( !*((_DWORD *)this + 10) )
  {
LABEL_6:
    v7 = -2147418113;
    goto LABEL_17;
  }
  v7 = ValidateContactIDCollection((struct IContact *)(((unsigned __int64)this - 32) & -(__int64)(this != (CContact *)64)));
  if ( v7 < 0 )
    goto LABEL_17;
  v8 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 79))(
         *((_QWORD *)this + 79),
         &GUID_00000109_0000_0000_c000_000000000046,
         &v12);
  v7 = v8;
  if ( v8 == -2147467262 )
  {
    v9 = (IStream *)*((_QWORD *)this + 78);
    if ( !v9 )
      goto LABEL_6;
    v7 = IStream_Size(v9, &pui);
    if ( v7 >= 0 )
    {
      v7 = IStream_Reset(*((IStream **)this + 78));
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, ULARGE_INTEGER, _QWORD, _QWORD))(**((_QWORD **)this + 78)
                                                                                                 + 56LL))(
               *((_QWORD *)this + 78),
               a2,
               pui,
               0,
               0);
        if ( v7 >= 0 )
          v7 = 0;
      }
    }
  }
  else if ( v8 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, struct IStream *, _QWORD))(*(_QWORD *)v12 + 48LL))(v12, a2, a3);
    if ( v7 >= 0 )
      v7 = 0;
  }
LABEL_17:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007dcd0  mov     [rsp+arg_8], rbx
0x18007dcd5  push    rbp
0x18007dcd6  push    rsi
0x18007dcd7  push    rdi
0x18007dcd8  sub     rsp, 30h
0x18007dcdc  mov     ebx, [rcx+2A8h]
0x18007dce2  mov     ebp, r8d
0x18007dce5  mov     rsi, rdx
0x18007dce8  mov     [rsp+48h+arg_18], 0
0x18007dcf1  mov     rdi, rcx
0x18007dcf4  mov     qword ptr [rsp+48h+pui], 0
0x18007dcfd  call    cs:__imp_GetCurrentThreadId
0x18007dd03  cmp     eax, ebx
0x18007dd05  jz      short loc_18007DD11
0x18007dd07  mov     ebx, 8001010Eh
0x18007dd0c  jmp     loc_18007DDFC
0x18007dd11  test    rsi, rsi
0x18007dd14  jnz     short loc_18007DD20
0x18007dd16  mov     ebx, 80070057h
0x18007dd1b  jmp     loc_18007DDFC
0x18007dd20  cmp     dword ptr [rdi+28h], 0
0x18007dd24  jnz     short loc_18007DD30
0x18007dd26  mov     ebx, 8000FFFFh
0x18007dd2b  jmp     loc_18007DDFC
0x18007dd30  lea     rdx, [rdi-20h]
0x18007dd34  lea     rax, [rdi-40h]
0x18007dd38  neg     rax
0x18007dd3b  sbb     rcx, rcx
0x18007dd3e  and     rcx, rdx; struct IContact *
0x18007dd41  call    _ValidateContactIDCollection
0x18007dd46  mov     ebx, eax
0x18007dd48  test    eax, eax
0x18007dd4a  js      loc_18007DDFC
0x18007dd50  mov     rcx, [rdi+278h]
0x18007dd57  lea     r8, [rsp+48h+arg_18]
0x18007dd5c  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18007dd63  mov     rax, [rcx]
0x18007dd66  mov     rax, [rax]
0x18007dd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd6e  mov     ebx, eax
0x18007dd70  cmp     eax, 80004002h
0x18007dd75  jnz     short loc_18007DDD8
0x18007dd77  mov     rcx, [rdi+270h]; pstm
0x18007dd7e  test    rcx, rcx
0x18007dd81  jz      short loc_18007DD26
0x18007dd83  lea     rdx, [rsp+48h+pui]; pui
0x18007dd88  call    cs:__imp_IStream_Size
0x18007dd8e  mov     ebx, eax
0x18007dd90  test    eax, eax
0x18007dd92  js      short loc_18007DDFC
0x18007dd94  mov     rcx, [rdi+270h]; pstm
0x18007dd9b  call    cs:__imp_IStream_Reset
0x18007dda1  mov     ebx, eax
0x18007dda3  test    eax, eax
0x18007dda5  js      short loc_18007DDFC
0x18007dda7  mov     rcx, [rdi+270h]
0x18007ddae  xor     r9d, r9d
0x18007ddb1  mov     r8, qword ptr [rsp+48h+pui]
0x18007ddb6  mov     rdx, rsi
0x18007ddb9  mov     [rsp+48h+var_28], 0
0x18007ddc2  mov     rax, [rcx]
0x18007ddc5  mov     rax, [rax+38h]
0x18007ddc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ddce  mov     ebx, eax
0x18007ddd0  test    eax, eax
0x18007ddd2  js      short loc_18007DDFC
0x18007ddd4  xor     ebx, ebx
0x18007ddd6  jmp     short loc_18007DDFC
0x18007ddd8  test    eax, eax
0x18007ddda  js      short loc_18007DDFC
0x18007dddc  mov     rcx, [rsp+48h+arg_18]
0x18007dde1  mov     r8d, ebp
0x18007dde4  mov     rdx, rsi
0x18007dde7  mov     rax, [rcx]
0x18007ddea  mov     rax, [rax+30h]
0x18007ddee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ddf3  mov     ebx, eax
0x18007ddf5  xor     eax, eax
0x18007ddf7  test    ebx, ebx
0x18007ddf9  cmovns  ebx, eax
0x18007ddfc  lea     rcx, [rsp+48h+arg_18]
0x18007de01  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007de06  mov     eax, ebx
0x18007de08  mov     rbx, [rsp+48h+arg_8]
0x18007de0d  add     rsp, 30h
0x18007de11  pop     rdi
0x18007de12  pop     rsi
0x18007de13  pop     rbp
0x18007de14  retn
```
