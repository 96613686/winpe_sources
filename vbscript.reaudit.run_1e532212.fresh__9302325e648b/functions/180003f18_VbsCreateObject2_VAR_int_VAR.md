# VbsCreateObject2(VAR *,int,VAR *)

- ea: `0x180003f18`
- end: `0x18000405e`
- name: `?VbsCreateObject2@@YAJPEAVVAR@@H0@Z`
- size: `326`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003eb0`

## callees

- `0x1800037b0`
- `0x180003a30`
- `0x180003f18`
- `0x180004610`
- `0x18001b260`
- `0x1800204f0`
- `0x180035ef0`
- `0x1800396a0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004056`
- `OLEAUT32!__imp_SysFreeString` at `0x180004056`

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
  HRESULT ObjectFromProgID; // ebx
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
  ObjectFromProgID = GetObjectFromProgID((struct CSession **)CurrentOleScript, v11, 0, a1, 0, v12);
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
0x180003f18  push    rbx
0x180003f1a  push    rbp
0x180003f1b  push    rsi
0x180003f1c  push    rdi
0x180003f1d  push    r12
0x180003f1f  push    r13
0x180003f21  push    r14
0x180003f23  push    r15
0x180003f25  sub     rsp, 48h
0x180003f29  mov     r13d, 1
0x180003f2f  movsxd  rbx, edx
0x180003f32  mov     rsi, r8
0x180003f35  mov     [rcx], r13w
0x180003f39  mov     r14, rcx
0x180003f3c  lea     eax, [rbx-1]
0x180003f3f  cmp     eax, r13d
0x180003f42  jbe     short loc_180003F5A
0x180003f44  mov     eax, 800A01C2h
0x180003f49  add     rsp, 48h
0x180003f4d  pop     r15
0x180003f4f  pop     r14
0x180003f51  pop     r13
0x180003f53  pop     r12
0x180003f55  pop     rdi
0x180003f56  pop     rsi
0x180003f57  pop     rbp
0x180003f58  pop     rbx
0x180003f59  retn
0x180003f5a  call    ?GetCurrentOleScript@CScriptRuntime@@SAPEAVCOleScript@@XZ; CScriptRuntime::GetCurrentOleScript(void)
0x180003f5f  mov     rdi, rax
0x180003f62  test    rax, rax
0x180003f65  jz      loc_180004049
0x180003f6b  lea     rax, [rbx-1]
0x180003f6f  xor     ebp, ebp
0x180003f71  lea     rcx, [rax+rax*2]
0x180003f75  xor     r15b, r15b
0x180003f78  lea     rcx, [rsi+rcx*8]; pvarSrc
0x180003f7c  mov     [rsp+88h+var_58], r15b
0x180003f81  lea     edx, [rbp+8]; unsigned __int16
0x180003f84  call    ?PvarGetTypeVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetTypeVal(int)
0x180003f89  mov     r12, [rax+8]
0x180003f8d  cmp     ebx, r13d
0x180003f90  jnz     short loc_180004004
0x180003f92  xor     eax, eax
0x180003f94  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180003f99  mov     r9, r14; struct VAR *
0x180003f9c  xor     r8d, r8d; pbstr
0x180003f9f  mov     [rsp+88h+var_68], 0; int
0x180003fa7  mov     rdx, r12; lpszProgID
0x180003faa  mov     rcx, rdi; this
0x180003fad  call    ?GetObjectFromProgID@@YAJPEAVCOleScript@@PEAG1PEAVVAR@@H1@Z; GetObjectFromProgID(COleScript *,ushort *,ushort *,VAR *,int,ushort *)
0x180003fb2  mov     ebx, eax
0x180003fb4  mov     esi, 800A01ADh
0x180003fb9  mov     eax, [rdi+2B0h]
0x180003fbf  test    al, 0Bh
0x180003fc1  jnz     short loc_180003FCE
0x180003fc3  xor     edx, edx; struct _GUID *
0x180003fc5  call    ?IsUnsafeAllowed@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::IsUnsafeAllowed(_GUID const *)
0x180003fca  test    eax, eax
0x180003fcc  jnz     short loc_180004039
0x180003fce  test    ebx, ebx
0x180003fd0  jns     short loc_18000403D
0x180003fd2  mov     ebx, esi
0x180003fd4  mov     ecx, ebx; int
0x180003fd6  call    ?MapHr@@YAJJ@Z; MapHr(long)
0x180003fdb  cmp     eax, esi
0x180003fdd  jnz     short loc_18000403D
0x180003fdf  mov     rcx, [rdi+280h]; this
0x180003fe6  test    rcx, rcx
0x180003fe9  jz      short loc_18000403D
0x180003feb  mov     r9, r12; unsigned __int16 *
0x180003fee  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x180003ff6  xor     r8d, r8d; struct VAR *
0x180003ff9  mov     edx, ebx; int
0x180003ffb  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x180004000  mov     ebx, eax
0x180004002  jmp     short loc_18000403D
0x180004004  mov     rdx, rsi; struct VAR *
0x180004007  mov     [rsp+88h+var_50], r12
0x18000400c  lea     rcx, [rsp+88h+var_58]; this
0x180004011  call    ?CloneIfNeeded@BSTRHelper@@QEAAXPEAVVAR@@@Z; BSTRHelper::CloneIfNeeded(VAR *)
0x180004016  mov     rbp, [rsp+88h+var_50]
0x18000401b  mov     edx, 8; unsigned __int16
0x180004020  mov     rcx, rsi; pvarSrc
0x180004023  mov     r12, rbp
0x180004026  call    ?PvarGetTypeVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetTypeVal(int)
0x18000402b  mov     r15b, [rsp+88h+var_58]
0x180004030  mov     rax, [rax+8]
0x180004034  jmp     loc_180003F94
0x180004039  test    ebx, ebx
0x18000403b  js      short loc_180003FD4
0x18000403d  test    r15b, r15b
0x180004040  jnz     short loc_180004053
0x180004042  mov     eax, ebx
0x180004044  jmp     loc_180003F49
0x180004049  mov     eax, 8000FFFFh
0x18000404e  jmp     loc_180003F49
0x180004053  mov     rcx, rbp; bstrString
0x180004056  call    cs:__imp_SysFreeString
0x18000405c  jmp     short loc_180004042
```
