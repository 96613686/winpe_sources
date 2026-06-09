# VbsCreateObject2(VAR *,int,VAR *)

- ea: `0x18002516c`
- end: `0x1800252b9`
- name: `?VbsCreateObject2@@YAJPEAVVAR@@H0@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct VAR *, int, VARIANTARG *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180025100`

## callees

- `0x18001a260`
- `0x18001c358`
- `0x18002516c`
- `0x18002580c`
- `0x18002583c`
- `0x1800260a0`
- `0x1800265a8`
- `0x180037464`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800252ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252ab`

## pseudocode

```c
__int64 __fastcall VbsCreateObject2(struct VAR *a1, int a2, VARIANTARG *a3)
{
  __int64 v3; // rbx
  struct COleScript *CurrentOleScript; // rdi
  OLECHAR *v8; // rbp
  char v9; // r15
  struct VAR *TypeVal; // rax
  const OLECHAR *v11; // r12
  unsigned __int16 *v12; // rax
  COleScript *v13; // rcx
  int ObjectFromProgID; // ebx
  CSession *v15; // rcx
  struct VAR *v16; // rax
  _BYTE v17[8]; // [rsp+30h] [rbp-58h] BYREF
  OLECHAR *v18; // [rsp+38h] [rbp-50h]

  v3 = a2;
  *(_WORD *)a1 = 1;
  if ( (unsigned int)(a2 - 1) > 1 )
    return 2148139458LL;
  CurrentOleScript = CScriptRuntime::GetCurrentOleScript();
  if ( !CurrentOleScript )
    return 2147549183LL;
  v8 = 0;
  v9 = 0;
  v17[0] = 0;
  TypeVal = VAR::PvarGetTypeVal(&a3[v3 - 1], 8u);
  v11 = (const OLECHAR *)*((_QWORD *)TypeVal + 1);
  if ( (_DWORD)v3 == 1 )
  {
    v12 = 0;
  }
  else
  {
    v18 = (OLECHAR *)*((_QWORD *)TypeVal + 1);
    BSTRHelper::CloneIfNeeded((BSTRHelper *)v17, (struct VAR *)a3);
    v8 = v18;
    v11 = v18;
    v16 = VAR::PvarGetTypeVal(a3, 8u);
    v9 = v17[0];
    v12 = (unsigned __int16 *)*((_QWORD *)v16 + 1);
  }
  ObjectFromProgID = GetObjectFromProgID(CurrentOleScript, v11, 0, a1, 0, v12);
  if ( (*((_DWORD *)CurrentOleScript + 172) & 0xB) == 0 && (unsigned int)COleScript::IsUnsafeAllowed(v13, 0) )
  {
    if ( ObjectFromProgID < 0 )
      goto LABEL_10;
  }
  else if ( ObjectFromProgID < 0 )
  {
    ObjectFromProgID = -2146827859;
LABEL_10:
    if ( (unsigned int)MapHr(ObjectFromProgID) == -2146827859 )
    {
      v15 = (CSession *)*((_QWORD *)CurrentOleScript + 80);
      if ( v15 )
        ObjectFromProgID = CSession::RecordHr(v15, ObjectFromProgID, 0, v11, -1);
    }
  }
  if ( v9 )
    SysFreeString(v8);
  return (unsigned int)ObjectFromProgID;
}

```

## disassembly

```asm
0x18002516c  push    rbx
0x18002516e  push    rbp
0x18002516f  push    rsi
0x180025170  push    rdi
0x180025171  push    r12
0x180025173  push    r13
0x180025175  push    r14
0x180025177  push    r15
0x180025179  sub     rsp, 48h
0x18002517d  mov     r13d, 1
0x180025183  movsxd  rbx, edx
0x180025186  mov     rsi, r8
0x180025189  mov     [rcx], r13w
0x18002518d  mov     r14, rcx
0x180025190  lea     eax, [rbx-1]
0x180025193  cmp     eax, r13d
0x180025196  jbe     short loc_1800251AF
0x180025198  mov     eax, 800A01C2h
0x18002519d  add     rsp, 48h
0x1800251a1  pop     r15
0x1800251a3  pop     r14
0x1800251a5  pop     r13
0x1800251a7  pop     r12
0x1800251a9  pop     rdi
0x1800251aa  pop     rsi
0x1800251ab  pop     rbp
0x1800251ac  pop     rbx
0x1800251ad  retn
0x1800251af  call    ?GetCurrentOleScript@CScriptRuntime@@SAPEAVCOleScript@@XZ; CScriptRuntime::GetCurrentOleScript(void)
0x1800251b4  mov     rdi, rax
0x1800251b7  test    rax, rax
0x1800251ba  jz      loc_18002529E
0x1800251c0  lea     rax, [rbx-1]
0x1800251c4  xor     ebp, ebp
0x1800251c6  lea     rcx, [rax+rax*2]
0x1800251ca  xor     r15b, r15b
0x1800251cd  lea     rcx, [rsi+rcx*8]; pvarSrc
0x1800251d1  mov     [rsp+88h+var_58], r15b
0x1800251d6  lea     edx, [rbp+8]; unsigned __int16
0x1800251d9  call    ?PvarGetTypeVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetTypeVal(int)
0x1800251de  mov     r12, [rax+8]
0x1800251e2  cmp     ebx, r13d
0x1800251e5  jnz     short loc_180025259
0x1800251e7  xor     eax, eax
0x1800251e9  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x1800251ee  mov     r9, r14; struct VAR *
0x1800251f1  xor     r8d, r8d; pbstr
0x1800251f4  mov     [rsp+88h+var_68], 0; int
0x1800251fc  mov     rdx, r12; lpszProgID
0x1800251ff  mov     rcx, rdi; this
0x180025202  call    ?GetObjectFromProgID@@YAJPEAVCOleScript@@PEAG1PEAVVAR@@H1@Z; GetObjectFromProgID(COleScript *,ushort *,ushort *,VAR *,int,ushort *)
0x180025207  mov     ebx, eax
0x180025209  mov     esi, 800A01ADh
0x18002520e  mov     eax, [rdi+2B0h]
0x180025214  test    al, 0Bh
0x180025216  jnz     short loc_180025223
0x180025218  xor     edx, edx; struct _GUID *
0x18002521a  call    ?IsUnsafeAllowed@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::IsUnsafeAllowed(_GUID const *)
0x18002521f  test    eax, eax
0x180025221  jnz     short loc_18002528E
0x180025223  test    ebx, ebx
0x180025225  jns     short loc_180025292
0x180025227  mov     ebx, esi
0x180025229  mov     ecx, ebx; int
0x18002522b  call    ?MapHr@@YAJJ@Z; MapHr(long)
0x180025230  cmp     eax, esi
0x180025232  jnz     short loc_180025292
0x180025234  mov     rcx, [rdi+280h]; this
0x18002523b  test    rcx, rcx
0x18002523e  jz      short loc_180025292
0x180025240  mov     r9, r12; unsigned __int16 *
0x180025243  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18002524b  xor     r8d, r8d; struct VAR *
0x18002524e  mov     edx, ebx; int
0x180025250  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x180025255  mov     ebx, eax
0x180025257  jmp     short loc_180025292
0x180025259  mov     rdx, rsi; struct VAR *
0x18002525c  mov     [rsp+88h+var_50], r12
0x180025261  lea     rcx, [rsp+88h+var_58]; this
0x180025266  call    ?CloneIfNeeded@BSTRHelper@@QEAAXPEAVVAR@@@Z; BSTRHelper::CloneIfNeeded(VAR *)
0x18002526b  mov     rbp, [rsp+88h+var_50]
0x180025270  mov     edx, 8; unsigned __int16
0x180025275  mov     rcx, rsi; pvarSrc
0x180025278  mov     r12, rbp
0x18002527b  call    ?PvarGetTypeVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetTypeVal(int)
0x180025280  mov     r15b, [rsp+88h+var_58]
0x180025285  mov     rax, [rax+8]
0x180025289  jmp     loc_1800251E9
0x18002528e  test    ebx, ebx
0x180025290  js      short loc_180025229
0x180025292  test    r15b, r15b
0x180025295  jnz     short loc_1800252A8
0x180025297  mov     eax, ebx
0x180025299  jmp     loc_18002519D
0x18002529e  mov     eax, 8000FFFFh
0x1800252a3  jmp     loc_18002519D
0x1800252a8  mov     rcx, rbp; bstrString
0x1800252ab  call    cs:__imp_SysFreeString
0x1800252b2  nop     dword ptr [rax+rax+00h]
0x1800252b7  jmp     short loc_180025297
```
