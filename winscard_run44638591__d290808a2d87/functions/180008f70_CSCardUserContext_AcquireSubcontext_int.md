# CSCardUserContext::AcquireSubcontext(int)

- ea: `0x180008f70`
- end: `0x1800093db`
- name: `?AcquireSubcontext@CSCardUserContext@@QEAAPEAVCSCardSubcontext@@H@Z`
- size: `1131`
- prototype: `struct CSCardSubcontext *(CSCardUserContext *__hidden this, int)`
- caller_count: `8`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800051b0`
- `0x180007f40`
- `0x18000e400`
- `0x180011b70`
- `0x180012000`
- `0x1800166b0`
- `0x18001a538`
- `0x180024634`

## callees

- `0x180006bf0`
- `0x180007940`
- `0x180008f70`
- `0x180014cd0`
- `0x180015468`
- `0x180015af0`
- `0x180015b6c`
- `0x18001b9b8`
- `0x18001b9c4`
- `0x18001ba04`
- `0x18002ef20`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800090b1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800090b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800093ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800093ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000931b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000931b`
- `RPCRT4!RpcBindingCreateW` at `0x18000915d`
- `RPCRT4!RpcBindingCreateW` at `0x18000915d`
- `RPCRT4!RpcBindingBind` at `0x180009236`
- `RPCRT4!RpcBindingBind` at `0x180009236`
- `RPCRT4!RpcBindingFree` at `0x180009179`
- `RPCRT4!RpcBindingFree` at `0x180009179`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
struct CSCardSubcontext *__fastcall CSCardUserContext::AcquireSubcontext(CSCardUserContext *this, int a2)
{
  char *v4; // rbx
  int v5; // r14d
  CSCardSubcontext *v7; // rsi
  char *v8; // r15
  int v9; // eax
  CSCardSubcontext *v10; // rax
  RPC_STATUS v11; // r15d
  HANDLE v12; // rax
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  __int64 v16; // r14
  int v17; // r15d
  unsigned __int64 v18; // rdx
  _QWORD *v19; // r13
  __int64 i; // r8
  void **v21; // r12
  int v22; // [rsp+20h] [rbp-68h]
  int pExceptionObject; // [rsp+28h] [rbp-60h] BYREF
  int v24; // [rsp+2Ch] [rbp-5Ch]
  int v25; // [rsp+30h] [rbp-58h] BYREF
  RPC_STATUS v26; // [rsp+34h] [rbp-54h] BYREF
  int v27[2]; // [rsp+38h] [rbp-50h]
  int v28[2]; // [rsp+40h] [rbp-48h]
  int v29; // [rsp+48h] [rbp-40h]
  int v30; // [rsp+50h] [rbp-38h]
  int v31; // [rsp+58h] [rbp-30h]

  *(_QWORD *)v27 = 0;
  v4 = (char *)this + 72;
  *(_QWORD *)v28 = (char *)this + 72;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 9))((char *)this + 72, 0, 0);
  v5 = *((_DWORD *)this + 15);
  while ( v5 )
  {
    if ( *((_DWORD *)this + 15) <= (unsigned int)--v5 )
    {
      *(_QWORD *)v27 = 0;
    }
    else
    {
      _mm_lfence();
      v7 = *(CSCardSubcontext **)(*((_QWORD *)this + 8) + 8LL * v5);
      *(_QWORD *)v27 = v7;
      if ( v7 )
      {
        v8 = (char *)v7 + 48;
        (**((void (__fastcall ***)(__int64, _QWORD, _QWORD))v7 + 6))((__int64)v7 + 48, 0, 0);
        v9 = *((_DWORD *)v7 + 4);
        if ( a2 )
        {
          if ( v9 == 1 )
          {
            (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v8)((__int64)v7 + 48, 0, 0);
            *((_DWORD *)v7 + 4) = 2;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))((__int64)v7 + 48);
            (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v8)((__int64)v7 + 48, 0, 0);
            *((_DWORD *)v7 + 5) = *((_DWORD *)v7 + 4);
            *((_DWORD *)v7 + 4) = 3;
            if ( !ResetEvent(*((HANDLE *)v7 + 3)) )
              GetLastError();
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))((__int64)v7 + 48);
LABEL_12:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))((__int64)v7 + 48);
LABEL_4:
            (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
            return v7;
          }
        }
        else if ( v9 < 3 )
        {
          CSCardSubcontext::SetBusy(v7);
          goto LABEL_12;
        }
        *(_QWORD *)v27 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  v10 = (CSCardSubcontext *)operator new(0x78u);
  if ( v10 )
    v7 = CSCardSubcontext::CSCardSubcontext(v10);
  else
    v7 = 0;
  *(_QWORD *)v27 = v7;
  if ( v7 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64))(*((_QWORD *)v7 + 6) + 16LL))((__int64)v7 + 48) )
    {
      if ( a2 )
        CSCardSubcontext::Allocate(v7);
      CSCardSubcontext::SetBusy(v7);
      *((_QWORD *)v7 + 13) = 0;
      v11 = RpcBindingCreateW(&CALRPC_Template, &CALRPC_Security, &CALRPC_Options, (RPC_BINDING_HANDLE *)v7 + 13);
      if ( v11 || (v11 = RpcBindingBind(0, *((RPC_BINDING_HANDLE *)v7 + 13), qword_180034370)) != 0 )
      {
        if ( *((_QWORD *)v7 + 13) )
        {
          RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 13);
          *((_QWORD *)v7 + 13) = 0;
        }
        v12 = SCardAccessStartedEvent();
        if ( v12 )
        {
          if ( WaitForSingleObject(v12, 0) )
            v11 = -2146435043;
          SCardReleaseStartedEvent();
        }
        else
        {
          v11 = 5;
        }
        v26 = v11;
        throw (ulong *)&v26;
      }
      v15 = CalRpcEstablishContext(
              *((_QWORD *)v7 + 13),
              (int)v7 + 112,
              v13,
              v14,
              v22,
              pExceptionObject,
              v25,
              v27[0],
              v28[0],
              v29,
              v30,
              v31);
      if ( v15 )
      {
        pExceptionObject = v15;
        throw (ulong *)&pExceptionObject;
      }
      v16 = *((unsigned int *)this + 15);
      v17 = *((_DWORD *)this + 14);
      LODWORD(v18) = v16;
      if ( (unsigned int)v16 < v17 )
      {
        v21 = (void **)((char *)this + 64);
      }
      else
      {
        if ( !v17 )
          v17 = 4;
        v24 = v17;
        while ( (int)v16 >= v17 )
        {
          v17 *= 2;
          v24 = v17;
        }
        v19 = operator new[](saturated_mul(v17, 8u));
        if ( !v19 )
        {
          v25 = 14;
          throw (ulong *)&v25;
        }
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v18 = *((unsigned int *)this + 15);
          v21 = (void **)((char *)this + 64);
          if ( (unsigned int)i >= (unsigned int)v18 )
            break;
          v19[i] = *((_QWORD *)*v21 + i);
        }
        if ( *v21 )
        {
          operator delete(*v21, v18);
          LODWORD(v18) = *((_DWORD *)this + 15);
        }
        *v21 = v19;
        *((_DWORD *)this + 14) = v17;
        if ( (unsigned int)v16 < (unsigned int)v18 )
          goto LABEL_43;
      }
      while ( (unsigned int)v18 < (unsigned int)v16 )
      {
        *(_QWORD *)(*((_QWORD *)this + 8) + 8LL * (unsigned int)v18) = 0;
        LODWORD(v18) = v18 + 1;
      }
      *((_DWORD *)this + 15) = v16 + 1;
LABEL_43:
      *((_QWORD *)*v21 + v16) = v7;
      *((_QWORD *)v7 + 5) = this;
      goto LABEL_4;
    }
    (**(void (__fastcall ***)(CSCardSubcontext *, __int64))v7)(v7, 1);
    *(_QWORD *)v27 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return 0;
  }
  else
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180008f70  mov     [rsp+arg_8], edx
0x180008f74  push    rbx
0x180008f75  push    rsi
0x180008f76  push    rdi
0x180008f77  push    r12
0x180008f79  push    r13
0x180008f7b  push    r14; pExceptionObject
0x180008f7d  push    r15; int
0x180008f7f  sub     rsp, 50h
0x180008f83  mov     r12d, edx
0x180008f86  mov     rdi, rcx
0x180008f89  xor     r13d, r13d
0x180008f8c  mov     esi, r13d
0x180008f8f  mov     qword ptr [rsp+88h+var_50], r13
0x180008f94  lea     rbx, [rcx+48h]
0x180008f98  mov     qword ptr [rsp+88h+var_48], rbx; int
0x180008f9d  mov     rax, [rbx]
0x180008fa0  xor     r8d, r8d
0x180008fa3  xor     edx, edx
0x180008fa5  mov     rcx, rbx
0x180008fa8  mov     rax, [rax]
0x180008fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb0  nop
0x180008fb1  mov     [rsp+88h+var_64], r13d
0x180008fb6  mov     r14d, [rdi+3Ch]
0x180008fba  mov     [rsp+88h+var_64], r14d
0x180008fbf  test    r14d, r14d
0x180008fc2  jnz     short loc_180008FEF
0x180008fc4  test    rsi, rsi
0x180008fc7  jz      loc_1800090E3
0x180008fcd  mov     rcx, [rbx]
0x180008fd0  mov     rax, [rcx+8]
0x180008fd4  mov     rcx, rbx
0x180008fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fdc  mov     rax, rsi
0x180008fdf  add     rsp, 50h
0x180008fe3  pop     r15
0x180008fe5  pop     r14
0x180008fe7  pop     r13
0x180008fe9  pop     r12
0x180008feb  pop     rdi
0x180008fec  pop     rsi
0x180008fed  pop     rbx
0x180008fee  retn
0x180008fef  dec     r14d
0x180008ff2  mov     [rsp+88h+var_64], r14d
0x180008ff7  cmp     [rdi+3Ch], r14d
0x180008ffb  jbe     loc_1800091F1
0x180009001  lfence
0x180009004  movsxd  rcx, r14d
0x180009007  mov     rax, [rdi+40h]
0x18000900b  mov     rsi, [rax+rcx*8]
0x18000900f  mov     qword ptr [rsp+88h+var_50], rsi
0x180009014  test    rsi, rsi
0x180009017  jz      loc_1800091EC
0x18000901d  lea     r15, [rsi+30h]
0x180009021  mov     [rsp+88h+arg_0], r15
0x180009029  mov     rax, [r15]
0x18000902c  xor     r8d, r8d
0x18000902f  xor     edx, edx
0x180009031  mov     rcx, r15
0x180009034  mov     rax, [rax]
0x180009037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000903c  nop
0x18000903d  mov     eax, [rsi+10h]
0x180009040  test    r12d, r12d
0x180009043  jz      loc_1800091A5
0x180009049  cmp     eax, 1
0x18000904c  jnz     loc_1800091D5
0x180009052  mov     [rsp+88h+arg_10], r15
0x18000905a  mov     rax, [r15]
0x18000905d  xor     r8d, r8d
0x180009060  xor     edx, edx
0x180009062  mov     rcx, r15
0x180009065  mov     rax, [rax]
0x180009068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000906d  nop
0x18000906e  mov     dword ptr [rsi+10h], 2
0x180009075  mov     rax, [r15]
0x180009078  mov     rcx, r15
0x18000907b  mov     rax, [rax+8]
0x18000907f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009084  mov     [rsp+88h+arg_10], r15
0x18000908c  mov     rax, [r15]
0x18000908f  xor     r8d, r8d
0x180009092  xor     edx, edx
0x180009094  mov     rcx, r15
0x180009097  mov     rax, [rax]
0x18000909a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909f  nop
0x1800090a0  mov     eax, [rsi+10h]
0x1800090a3  mov     [rsi+14h], eax
0x1800090a6  mov     dword ptr [rsi+10h], 3
0x1800090ad  mov     rcx, [rsi+18h]; hEvent
0x1800090b1  call    cs:__imp_ResetEvent
0x1800090b7  test    eax, eax
0x1800090b9  jz      loc_18000931B
0x1800090bf  mov     rax, [r15]
0x1800090c2  mov     rcx, r15
0x1800090c5  mov     rax, [rax+8]
0x1800090c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ce  nop
0x1800090cf  mov     rax, [r15]
0x1800090d2  mov     rcx, r15
0x1800090d5  mov     rax, [rax+8]
0x1800090d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090de  jmp     loc_180008FCD
0x1800090e3  mov     ecx, 78h ; 'x'; Size
0x1800090e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800090ed  mov     [rsp+88h+arg_0], rax
0x1800090f5  test    rax, rax
0x1800090f8  jz      loc_1800091CD
0x1800090fe  mov     rcx, rax; this
0x180009101  call    ??0CSCardSubcontext@@QEAA@XZ; CSCardSubcontext::CSCardSubcontext(void)
0x180009106  mov     rsi, rax
0x180009109  mov     qword ptr [rsp+88h+var_50], rsi; int
0x18000910e  test    rsi, rsi
0x180009111  jz      loc_1800091B7
0x180009117  lea     rcx, [rsi+30h]
0x18000911b  mov     rax, [rcx]
0x18000911e  mov     rax, [rax+10h]
0x180009122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009127  test    eax, eax
0x180009129  jnz     loc_1800091FB
0x18000912f  test    r12d, r12d
0x180009132  jnz     loc_180009326
0x180009138  mov     rcx, rsi; this
0x18000913b  call    ?SetBusy@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::SetBusy(void)
0x180009140  mov     [rsi+68h], r13
0x180009144  lea     r9, [rsi+68h]; Binding
0x180009148  lea     r8, ?CALRPC_Options@@3U_RPC_BINDING_HANDLE_OPTIONS_V1@@A; Options
0x18000914f  lea     rdx, ?CALRPC_Security@@3U_RPC_BINDING_HANDLE_SECURITY_V1_W@@A; Security
0x180009156  lea     rcx, ?CALRPC_Template@@3U_RPC_BINDING_HANDLE_TEMPLATE_V1_W@@A; Template
0x18000915d  call    cs:__imp_RpcBindingCreateW
0x180009163  mov     r15d, eax
0x180009166  test    eax, eax
0x180009168  jz      loc_180009229
0x18000916e  cmp     qword ptr [rsi+68h], 0
0x180009173  jz      short loc_18000918C
0x180009175  lea     rcx, [rsi+68h]; Binding
0x180009179  call    cs:__imp_RpcBindingFree
0x18000917f  mov     [rsi+68h], r13
0x180009183  test    r15d, r15d
0x180009186  jz      loc_180009247
0x18000918c  call    SCardAccessStartedEvent
0x180009191  test    rax, rax
0x180009194  jnz     loc_1800093A8
0x18000919a  mov     r15d, 5
0x1800091a0  jmp     loc_1800093C3
0x1800091a5  cmp     eax, 3
0x1800091a8  jge     short loc_1800091D5
0x1800091aa  mov     rcx, rsi; this
0x1800091ad  call    ?SetBusy@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::SetBusy(void)
0x1800091b2  jmp     loc_1800090CF
0x1800091b7  mov     rax, [rbx]
0x1800091ba  mov     rcx, rbx
0x1800091bd  mov     rax, [rax+8]
0x1800091c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091c6  xor     eax, eax
0x1800091c8  jmp     loc_180008FDF
0x1800091cd  mov     rsi, r13
0x1800091d0  jmp     loc_180009109
0x1800091d5  mov     rsi, r13
0x1800091d8  mov     qword ptr [rsp+88h+var_50], r13
0x1800091dd  mov     rax, [r15]
0x1800091e0  mov     rcx, r15
0x1800091e3  mov     rax, [rax+8]
0x1800091e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ec  jmp     loc_180008FBF
0x1800091f1  mov     rsi, r13
0x1800091f4  mov     qword ptr [rsp+88h+var_50], r13
0x1800091f9  jmp     short loc_1800091EC
0x1800091fb  mov     rax, [rsi]
0x1800091fe  mov     edx, 1
0x180009203  mov     rcx, rsi
0x180009206  mov     rax, [rax]
0x180009209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920e  mov     qword ptr [rsp+88h+var_50], r13
0x180009213  mov     rax, [rbx]
0x180009216  mov     rcx, rbx
0x180009219  mov     rax, [rax+8]
0x18000921d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009222  xor     eax, eax
0x180009224  jmp     loc_180008FDF
0x180009229  lea     r8, qword_180034370; IfSpec
0x180009230  mov     rdx, [rsi+68h]; Binding
0x180009234  xor     ecx, ecx; pAsync
0x180009236  call    cs:__imp_RpcBindingBind
0x18000923c  mov     r15d, eax
0x18000923f  test    eax, eax
0x180009241  jnz     loc_18000916E
0x180009247  lea     rdx, [rsi+70h]; int
0x18000924b  mov     rcx, [rsi+68h]; int
0x18000924f  call    CalRpcEstablishContext
0x180009254  test    eax, eax
0x180009256  jnz     loc_180009333
0x18000925c  mov     r14d, [rdi+3Ch]
0x180009260  mov     [rsp+88h+var_68], r13d
0x180009265  mov     r15d, [rdi+38h]
0x180009269  mov     edx, r14d
0x18000926c  cmp     r14d, r15d
0x18000926f  jb      loc_1800092FC
0x180009275  mov     eax, 4
0x18000927a  test    r15d, r15d
0x18000927d  cmovz   r15d, eax
0x180009281  mov     [rsp+88h+var_5C], r15d
0x180009286  cmp     r14d, r15d
0x180009289  jge     loc_180009348
0x18000928f  movsxd  rcx, r15d
0x180009292  mov     eax, 8
0x180009297  mul     rcx
0x18000929a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800092a1  cmovb   rax, rcx
0x1800092a5  mov     rcx, rax; unsigned __int64
0x1800092a8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800092ad  mov     r13, rax
0x1800092b0  test    rax, rax
0x1800092b3  jz      loc_180009355
0x1800092b9  xor     r8d, r8d
0x1800092bc  mov     [rsp+88h+var_68], r8d
0x1800092c1  mov     edx, [rdi+3Ch]; unsigned __int64
0x1800092c4  lea     r12, [rdi+40h]
0x1800092c8  cmp     r8d, edx
0x1800092cb  jb      loc_18000936E
0x1800092d1  mov     rcx, [r12]; void *
0x1800092d5  test    rcx, rcx
0x1800092d8  jnz     loc_18000938A
0x1800092de  mov     [r12], r13
0x1800092e2  mov     [rdi+38h], r15d
0x1800092e6  cmp     r14d, edx
0x1800092e9  jnb     short loc_180009316
0x1800092eb  mov     rax, [r12]
0x1800092ef  mov     [rax+r14*8], rsi
0x1800092f3  mov     [rsi+28h], rdi
0x1800092f7  jmp     loc_180008FCD
0x1800092fc  lea     r12, [rdi+40h]
0x180009300  mov     [rsp+88h+var_68], edx
0x180009304  cmp     edx, r14d
0x180009307  jb      loc_180009397
0x18000930d  lea     eax, [r14+1]
0x180009311  mov     [rdi+3Ch], eax
0x180009314  jmp     short loc_1800092EB
0x180009316  xor     r13d, r13d
0x180009319  jmp     short loc_180009300
0x18000931b  call    cs:__imp_GetLastError
0x180009321  jmp     loc_1800090BF
0x180009326  mov     rcx, rsi; this
0x180009329  call    ?Allocate@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::Allocate(void)
0x18000932e  jmp     loc_180009138
0x180009333  mov     [rsp+88h+pExceptionObject], eax
0x180009337  lea     rdx, _TI1K; pThrowInfo
0x18000933e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180009343  call    _CxxThrowException_0
0x180009348  add     r15d, r15d
0x18000934b  mov     [rsp+88h+var_5C], r15d
0x180009350  jmp     loc_180009286
0x180009355  mov     [rsp+88h+var_58], 0Eh
0x18000935d  lea     rdx, _TI1K; pThrowInfo
0x180009364  lea     rcx, [rsp+88h+var_58]; pExceptionObject
0x180009369  call    _CxxThrowException_0
0x18000936e  lea     rdx, ds:0[r8*8]
0x180009376  mov     rax, [r12]
0x18000937a  mov     rcx, [rdx+rax]
0x18000937e  mov     [rdx+r13], rcx
0x180009382  inc     r8d
0x180009385  jmp     loc_1800092BC
0x18000938a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000938f  mov     edx, [rdi+3Ch]
0x180009392  jmp     loc_1800092DE
0x180009397  mov     ecx, edx
0x180009399  mov     rax, [rdi+40h]
0x18000939d  mov     [rax+rcx*8], r13
0x1800093a1  inc     edx
0x1800093a3  jmp     loc_180009300
0x1800093a8  xor     edx, edx; dwMilliseconds
0x1800093aa  mov     rcx, rax; hHandle
0x1800093ad  call    cs:__imp_WaitForSingleObject
0x1800093b3  mov     ecx, 8010001Dh
0x1800093b8  test    eax, eax
0x1800093ba  cmovnz  r15d, ecx
0x1800093be  call    SCardReleaseStartedEvent
0x1800093c3  mov     [rsp+88h+var_54], r15d
0x1800093c8  lea     rdx, _TI1K; pThrowInfo
0x1800093cf  lea     rcx, [rsp+88h+var_54]; pExceptionObject
0x1800093d4  call    _CxxThrowException_0
```
