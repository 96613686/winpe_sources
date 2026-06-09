# CASFMarkerObjectBase::CreateMarker(IASFMarker * *)

- ea: `0x1800268b0`
- end: `0x1800269fd`
- name: `?CreateMarker@CASFMarkerObjectBase@@UEAAJPEAPEAUIASFMarker@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CASFMarkerObjectBase *__hidden this, struct IASFMarker **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001174`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000e5c4`
- `0x1800268b0`
- `0x180027d44`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarkerObjectBase::CreateMarker(struct IWMSCriticalSection **this, struct IASFMarker **a2)
{
  int v4; // ebx
  CASFMarker *v5; // rax
  CASFMarker *v6; // rax
  struct IASFMarker *v7; // rdi
  _BYTE v9[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+28h] [rbp-30h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v9, this[4]);
  if ( this[5] )
  {
    if ( a2 )
    {
      v5 = (CASFMarker *)operator new(0x2A8u);
      if ( v5 )
      {
        v6 = CASFMarker::CASFMarker(v5);
        v7 = v6;
        if ( v6 )
        {
          v10 = 0;
          if ( (**(int (__fastcall ***)(CASFMarker *, GUID *, __int64 *))v6)(v6, &IID_IASFMarkerPriv, &v10) >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, struct IWMSCriticalSection *, struct IWMSCriticalSection **))(*(_QWORD *)v10 + 24LL))(
                   v10,
                   this[5],
                   this);
            if ( v10 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              v10 = 0;
            }
            if ( v4 < 0 )
            {
              (*(void (__fastcall **)(struct IASFMarker *))(*(_QWORD *)v7 + 16LL))(v7);
              goto LABEL_15;
            }
          }
          if ( (unsigned int)CTDynArray<IASFMarker *,20>::Add(this + 27, v7) )
          {
            *a2 = v7;
            (*(void (__fastcall **)(struct IASFMarker *))(*(_QWORD *)v7 + 8LL))(v7);
            v4 = 0;
            goto LABEL_15;
          }
          (*(void (__fastcall **)(struct IASFMarker *))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
      v4 = -2147024882;
      goto LABEL_15;
    }
    v4 = -2147024809;
  }
  else
  {
    v4 = -1072887818;
  }
LABEL_15:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800268b0  mov     [rsp+arg_10], rbx
0x1800268b5  push    rsi
0x1800268b6  push    rdi
0x1800268b7  push    r14
0x1800268b9  sub     rsp, 40h
0x1800268bd  mov     rax, cs:__security_cookie
0x1800268c4  xor     rax, rsp
0x1800268c7  mov     [rsp+58h+var_28], rax
0x1800268cc  mov     r14, rdx
0x1800268cf  mov     rsi, rcx
0x1800268d2  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800268d6  lea     rcx, [rsp+58h+var_38]; this
0x1800268db  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800268e0  cmp     qword ptr [rsi+28h], 0
0x1800268e5  jnz     short loc_1800268F1
0x1800268e7  mov     ebx, 0C00D07F6h
0x1800268ec  jmp     loc_1800269C3
0x1800268f1  test    r14, r14
0x1800268f4  jnz     short loc_180026900
0x1800268f6  mov     ebx, 80070057h
0x1800268fb  jmp     loc_1800269C3
0x180026900  mov     ecx, 2A8h; Size
0x180026905  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002690a  test    rax, rax
0x18002690d  jz      loc_1800269BE
0x180026913  mov     rcx, rax; this
0x180026916  call    ??0CASFMarker@@QEAA@XZ; CASFMarker::CASFMarker(void)
0x18002691b  mov     rdi, rax
0x18002691e  test    rax, rax
0x180026921  jz      loc_1800269BE
0x180026927  mov     [rsp+58h+var_30], 0
0x180026930  lea     r8, [rsp+58h+var_30]
0x180026935  mov     rcx, [rax]
0x180026938  lea     rdx, IID_IASFMarkerPriv
0x18002693f  mov     rax, [rcx]
0x180026942  mov     rcx, rdi
0x180026945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002694a  test    eax, eax
0x18002694c  js      short loc_18002699C
0x18002694e  mov     rcx, [rsp+58h+var_30]
0x180026953  mov     r8, rsi
0x180026956  mov     rdx, [rsi+28h]
0x18002695a  mov     rax, [rcx]
0x18002695d  mov     rax, [rax+18h]
0x180026961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026966  mov     rcx, [rsp+58h+var_30]
0x18002696b  mov     ebx, eax
0x18002696d  test    rcx, rcx
0x180026970  jz      short loc_180026987
0x180026972  mov     rdx, [rcx]
0x180026975  mov     rax, [rdx+10h]
0x180026979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002697e  mov     [rsp+58h+var_30], 0
0x180026987  test    ebx, ebx
0x180026989  jns     short loc_18002699C
0x18002698b  mov     rax, [rdi]
0x18002698e  mov     rcx, rdi
0x180026991  mov     rax, [rax+10h]
0x180026995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002699a  jmp     short loc_1800269C3
0x18002699c  lea     rcx, [rsi+0D8h]
0x1800269a3  mov     rdx, rdi
0x1800269a6  call    ?Add@?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEAAHPEAUIASFMarker@@PEAK@Z; CTDynArray<IASFMarker *,20>::Add(IASFMarker *,ulong *)
0x1800269ab  mov     rcx, rdi
0x1800269ae  test    eax, eax
0x1800269b0  jnz     short loc_1800269EA
0x1800269b2  mov     rax, [rdi]
0x1800269b5  mov     rax, [rax+10h]
0x1800269b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269be  mov     ebx, 8007000Eh
0x1800269c3  lea     rcx, [rsp+58h+var_38]; this
0x1800269c8  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800269cd  mov     eax, ebx
0x1800269cf  mov     rcx, [rsp+58h+var_28]
0x1800269d4  xor     rcx, rsp; StackCookie
0x1800269d7  call    __security_check_cookie
0x1800269dc  mov     rbx, [rsp+58h+arg_10]
0x1800269e1  add     rsp, 40h
0x1800269e5  pop     r14
0x1800269e7  pop     rdi
0x1800269e8  pop     rsi
0x1800269e9  retn
0x1800269ea  mov     [r14], rdi
0x1800269ed  mov     rax, [rdi]
0x1800269f0  mov     rax, [rax+8]
0x1800269f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269f9  xor     ebx, ebx
0x1800269fb  jmp     short loc_1800269C3
```
