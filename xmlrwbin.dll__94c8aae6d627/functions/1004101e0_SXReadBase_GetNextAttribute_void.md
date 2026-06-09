# SXReadBase::GetNextAttribute(void)

- ea: `0x1004101e0`
- end: `0x100410537`
- name: `?GetNextAttribute@SXReadBase@@IEAA_NXZ`
- size: `855`
- prototype: `bool __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x100405790`

## callees

- `0x100401350`
- `0x100406550`
- `0x100406be0`
- `0x100407050`
- `0x10040ff60`
- `0x100410010`
- `0x1004101e0`
- `0x100411160`
- `0x100424580`

## pseudocode

```c
bool __fastcall SXReadBase::GetNextAttribute(SXReadBase *this)
{
  unsigned __int8 v2; // al
  unsigned int Mb32; // edi
  __int64 v4; // rcx
  unsigned int v5; // edx
  __int64 v6; // rcx
  bool result; // al
  unsigned int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  struct CStringPtr **v11; // rsi
  bool v12; // cf

  *((_QWORD *)this + 157) = 0;
  *((_QWORD *)this + 160) = 0;
  *((_DWORD *)this + 322) = 0;
  *((_QWORD *)this + 162) = 0;
  *((_DWORD *)this + 316) = 0;
  *((_DWORD *)this + 290) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( *((_QWORD *)this + 178) != *((_QWORD *)this + 179) || (v2 = SXReadBase::Pull(this)) != 0 )
            v2 = **((_BYTE **)this + 178);
          if ( v2 != 233 )
            break;
          if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) && !SXReadBase::Pull(this) )
            goto LABEL_39;
          ++*((_QWORD *)this + 178);
          v6 = *((_QWORD *)this + 90);
          if ( v6 )
          {
            *((_QWORD *)this + 90) = *(_QWORD *)(v6 + 168);
            (**(void (__fastcall ***)(__int64, __int64))v6)(v6, 1);
          }
          else
          {
            *((_QWORD *)this + 90) = 0;
          }
          SXTokenTable::PushTokenTable(*((struct IMalloc **)this + 1), (struct SXTokenTable **)this + 90);
        }
        if ( v2 != 234 )
          break;
        if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) && !SXReadBase::Pull(this) )
          goto LABEL_39;
        ++*((_QWORD *)this + 178);
        Mb32 = SXReadBase::GetMb32(this);
        if ( Mb32 )
        {
          while ( 1 )
          {
            v4 = Mb32;
            v5 = *((_DWORD *)this + 358) - *((_DWORD *)this + 356);
            if ( v5 < Mb32 )
              v4 = v5;
            *((_QWORD *)this + 178) += v4;
            Mb32 -= v4;
            if ( !Mb32 )
              break;
            if ( !SXReadBase::Pull(this) )
            {
              MXRRaiseException(-1072896679);
              JUMPOUT(0x100410536LL);
            }
          }
        }
      }
      if ( v2 != 239 )
        break;
      if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) && !SXReadBase::Pull(this) )
        goto LABEL_39;
      ++*((_QWORD *)this + 178);
      SXReadBase::TokenT((SXTokenTable **)this);
    }
    if ( v2 != 240 )
      break;
    if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) && !SXReadBase::Pull(this) )
      goto LABEL_39;
    ++*((_QWORD *)this + 178);
    SXReadBase::NameT((SXTokenTable **)this);
  }
  if ( v2 != 246 )
    return 0;
  if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) && !SXReadBase::Pull(this)
    || (++*((_QWORD *)this + 178),
        v8 = SXReadBase::GetMb32(this),
        v9 = *((_QWORD *)this + 90),
        v8 >= *(_DWORD *)(v9 + 116)) )
  {
LABEL_39:
    MXRRaiseException(-2147467259);
    __debugbreak();
  }
  _mm_lfence();
  v10 = *(_QWORD *)(v9 + 120);
  *((_DWORD *)this + 312) = v8;
  v11 = (struct CStringPtr **)(v10 + 40LL * v8);
  RStringPtr::assign((SXReadBase *)((char *)this + 1224), *v11);
  RStringPtr::assign((SXReadBase *)((char *)this + 1232), v11[1]);
  RStringPtr::assign((SXReadBase *)((char *)this + 1272), v11[1]);
  RStringPtr::assign((SXReadBase *)((char *)this + 1240), v11[2]);
  if ( !*(_DWORD *)(*((_QWORD *)this + 155) + 16LL) )
  {
    _mm_lfence();
    v12 = *((_DWORD *)v11[1] + 4) < 6u;
    _mm_lfence();
    if ( !v12 )
    {
      *((_DWORD *)this + 316) = *((_DWORD *)v11[1] + 4) - 6;
      result = 1;
      *((_QWORD *)this + 157) = (char *)v11[1] + 36;
      return result;
    }
    *((_DWORD *)this + 316) = 0;
    *((_QWORD *)this + 157) = &nullwstr;
    RStringPtr::assign((SXReadBase *)((char *)this + 1272), rspNull);
  }
  return 1;
}

```

## disassembly

```asm
0x1004101e0  mov     [rsp+arg_10], rbx
0x1004101e5  mov     [rsp+arg_18], rdi
0x1004101ea  push    r14
0x1004101ec  sub     rsp, 20h
0x1004101f0  xor     r14d, r14d
0x1004101f3  mov     rbx, rcx
0x1004101f6  mov     [rcx+4E8h], r14
0x1004101fd  mov     [rcx+500h], r14
0x100410204  mov     [rcx+508h], r14d
0x10041020b  mov     [rcx+510h], r14
0x100410212  mov     [rcx+4F0h], r14d
0x100410219  mov     [rcx+488h], r14d
0x100410220  mov     rax, [rbx+598h]
0x100410227  cmp     [rbx+590h], rax
0x10041022e  jnz     short loc_10041023C
0x100410230  mov     rcx, rbx; this
0x100410233  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100410238  test    al, al
0x10041023a  jz      short loc_100410246
0x10041023c  mov     rax, [rbx+590h]
0x100410243  movzx   eax, byte ptr [rax]
0x100410246  movzx   ecx, al
0x100410249  sub     ecx, 0E9h
0x10041024f  jz      loc_100410344
0x100410255  sub     ecx, 1
0x100410258  jz      short loc_1004102CD
0x10041025a  sub     ecx, 5
0x10041025d  jz      short loc_100410299
0x10041025f  sub     ecx, 1
0x100410262  jnz     loc_1004103B4
0x100410268  mov     rax, [rbx+598h]
0x10041026f  cmp     [rbx+590h], rax
0x100410276  jnz     short loc_100410288
0x100410278  mov     rcx, rbx; this
0x10041027b  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100410280  test    al, al
0x100410282  jz      loc_100410521
0x100410288  inc     qword ptr [rbx+590h]
0x10041028f  mov     rcx, rbx; this
0x100410292  call    ?NameT@SXReadBase@@IEAAXXZ; SXReadBase::NameT(void)
0x100410297  jmp     short loc_100410220
0x100410299  mov     rax, [rbx+598h]
0x1004102a0  cmp     [rbx+590h], rax
0x1004102a7  jnz     short loc_1004102B9
0x1004102a9  mov     rcx, rbx; this
0x1004102ac  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x1004102b1  test    al, al
0x1004102b3  jz      loc_100410521
0x1004102b9  inc     qword ptr [rbx+590h]
0x1004102c0  mov     rcx, rbx; this
0x1004102c3  call    ?TokenT@SXReadBase@@IEAAXXZ; SXReadBase::TokenT(void)
0x1004102c8  jmp     loc_100410220
0x1004102cd  mov     rax, [rbx+598h]
0x1004102d4  cmp     [rbx+590h], rax
0x1004102db  jnz     short loc_1004102ED
0x1004102dd  mov     rcx, rbx; this
0x1004102e0  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x1004102e5  test    al, al
0x1004102e7  jz      loc_100410521
0x1004102ed  inc     qword ptr [rbx+590h]
0x1004102f4  mov     rcx, rbx; this
0x1004102f7  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x1004102fc  mov     edi, eax
0x1004102fe  test    eax, eax
0x100410300  jz      loc_100410220
0x100410306  nop     word ptr [rax+rax+00000000h]
0x100410310  mov     edx, [rbx+598h]
0x100410316  mov     ecx, edi
0x100410318  sub     edx, [rbx+590h]
0x10041031e  cmp     edx, edi
0x100410320  cmovb   ecx, edx
0x100410323  add     [rbx+590h], rcx
0x10041032a  sub     edi, ecx
0x10041032c  jz      loc_100410220
0x100410332  mov     rcx, rbx; this
0x100410335  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10041033a  test    al, al
0x10041033c  jz      loc_10041052C
0x100410342  jmp     short loc_100410310
0x100410344  mov     rax, [rbx+598h]
0x10041034b  cmp     [rbx+590h], rax
0x100410352  jnz     short loc_100410364
0x100410354  mov     rcx, rbx; this
0x100410357  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10041035c  test    al, al
0x10041035e  jz      loc_100410521
0x100410364  inc     qword ptr [rbx+590h]
0x10041036b  mov     rcx, [rbx+2D0h]
0x100410372  test    rcx, rcx
0x100410375  jz      short loc_100410398
0x100410377  mov     rax, [rcx+0A8h]
0x10041037e  mov     edx, 1
0x100410383  mov     [rbx+2D0h], rax
0x10041038a  mov     rax, [rcx]
0x10041038d  mov     rax, [rax]
0x100410390  call    cs:__guard_dispatch_icall_fptr
0x100410396  jmp     short loc_10041039F
0x100410398  mov     [rbx+2D0h], r14
0x10041039f  mov     rcx, [rbx+8]; struct IMalloc *
0x1004103a3  lea     rdx, [rbx+2D0h]; struct SXTokenTable **
0x1004103aa  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x1004103af  jmp     loc_100410220
0x1004103b4  cmp     ecx, 6
0x1004103b7  jz      short loc_1004103CC
0x1004103b9  xor     al, al
0x1004103bb  mov     rbx, [rsp+28h+arg_10]
0x1004103c0  mov     rdi, [rsp+28h+arg_18]
0x1004103c5  add     rsp, 20h
0x1004103c9  pop     r14
0x1004103cb  retn
0x1004103cc  mov     rax, [rbx+598h]
0x1004103d3  cmp     [rbx+590h], rax
0x1004103da  jnz     short loc_1004103EC
0x1004103dc  mov     rcx, rbx; this
0x1004103df  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x1004103e4  test    al, al
0x1004103e6  jz      loc_100410521
0x1004103ec  inc     qword ptr [rbx+590h]
0x1004103f3  mov     rcx, rbx; this
0x1004103f6  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x1004103fb  mov     r8, [rbx+2D0h]
0x100410402  cmp     eax, [r8+74h]
0x100410406  jnb     loc_100410521
0x10041040c  mov     [rsp+28h+arg_0], rbp
0x100410411  mov     [rsp+28h+arg_8], rsi
0x100410416  lfence
0x100410419  mov     ecx, eax
0x10041041b  lea     rdx, [rcx+rcx*4]
0x10041041f  mov     rcx, [r8+78h]
0x100410423  mov     [rbx+4E0h], eax
0x100410429  lea     rsi, [rcx+rdx*8]
0x10041042d  mov     rdx, [rcx+rdx*8]; struct CStringPtr *
0x100410431  lea     rcx, [rbx+4C8h]; this
0x100410438  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10041043d  mov     rdx, [rsi+8]; struct CStringPtr *
0x100410441  lea     rcx, [rbx+4D0h]; this
0x100410448  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10041044d  mov     rdx, [rsi+8]; struct CStringPtr *
0x100410451  lea     rcx, [rbx+4F8h]; this
0x100410458  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10041045d  mov     rdx, [rsi+10h]; struct CStringPtr *
0x100410461  lea     rcx, [rbx+4D8h]; this
0x100410468  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10041046d  mov     rax, [rbx+4D8h]
0x100410474  cmp     [rax+10h], r14d
0x100410478  jnz     loc_100410504
0x10041047e  lfence
0x100410481  mov     rcx, [rsi+8]
0x100410485  mov     eax, cs:dword_10042F8A0
0x10041048b  cmp     [rcx+10h], eax
0x10041048e  lfence
0x100410491  jb      short loc_1004104DC
0x100410493  mov     rax, [rsi+8]
0x100410497  mov     rbp, [rsp+28h+arg_0]
0x10041049c  mov     ecx, [rax+10h]
0x10041049f  sub     ecx, cs:dword_10042F8A0
0x1004104a5  mov     [rbx+4F0h], ecx
0x1004104ab  mov     rax, [rsi+8]
0x1004104af  mov     ecx, cs:dword_10042F8A0
0x1004104b5  mov     rsi, [rsp+28h+arg_8]
0x1004104ba  add     rcx, 0Ch
0x1004104be  lea     rcx, [rax+rcx*2]
0x1004104c2  mov     al, 1
0x1004104c4  mov     [rbx+4E8h], rcx
0x1004104cb  mov     rbx, [rsp+28h+arg_10]
0x1004104d0  mov     rdi, [rsp+28h+arg_18]
0x1004104d5  add     rsp, 20h
0x1004104d9  pop     r14
0x1004104db  retn
0x1004104dc  lea     rax, ?nullwstr@@3PA_WA; wchar_t near * nullwstr
0x1004104e3  mov     [rbx+4F0h], r14d
0x1004104ea  mov     [rbx+4E8h], rax
0x1004104f1  lea     rcx, [rbx+4F8h]; this
0x1004104f8  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x1004104ff  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100410504  mov     rsi, [rsp+28h+arg_8]
0x100410509  mov     al, 1
0x10041050b  mov     rbp, [rsp+28h+arg_0]
0x100410510  mov     rbx, [rsp+28h+arg_10]
0x100410515  mov     rdi, [rsp+28h+arg_18]
0x10041051a  add     rsp, 20h
0x10041051e  pop     r14
0x100410520  retn
0x100410521  mov     ecx, 80004005h; int
0x100410526  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041052b  int     3; Trap to Debugger
0x10041052c  mov     ecx, 0C00CE559h; int
0x100410531  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
