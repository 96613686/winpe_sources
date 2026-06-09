# CASFMarkerObjectBase::RemoveIndexSpecifier(ushort)

- ea: `0x180027330`
- end: `0x180027458`
- name: `?RemoveIndexSpecifier@CASFMarkerObjectBase@@UEAAJG@Z`
- size: `296`
- prototype: `__int64 __fastcall(CASFMarkerObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800266c0`
- `0x180027330`
- `0x18002773c`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarkerObjectBase::RemoveIndexSpecifier(struct IWMSCriticalSection **this, unsigned __int16 a2)
{
  unsigned int v2; // r14d
  unsigned int v4; // ebx
  unsigned int v5; // ecx
  int v6; // esi
  unsigned int i; // edi
  int (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+28h] [rbp-30h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v10, this[4]);
  if ( this[5] )
  {
    v5 = *((_DWORD *)this + 52);
    if ( v2 < v5 )
    {
      if ( v2 + 1 <= v5 )
      {
        v6 = 0;
        do
        {
          if ( (int)CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(this + 10, v2) < 0 )
            break;
          --*((_DWORD *)this + 52);
          ++v6;
        }
        while ( !v6 );
      }
      for ( i = 0; i < *((_DWORD *)this + 108); ++i )
      {
        v11 = 0;
        v8 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))CTDynArray<IASFMarker *,20>::operator[](this + 27, i);
        if ( (**v8)(v8, &IID_IASFMarkerPriv, &v11) >= 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 56LL))(v11, (unsigned __int16)v2);
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      v4 = 0;
    }
    else
    {
      v4 = -1072887824;
    }
  }
  else
  {
    v4 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v10);
  return v4;
}

```

## disassembly

```asm
0x180027330  mov     [rsp+arg_10], rbx
0x180027335  mov     [rsp+arg_18], rbp
0x18002733a  push    rsi
0x18002733b  push    rdi
0x18002733c  push    r14
0x18002733e  sub     rsp, 40h
0x180027342  mov     rax, cs:__security_cookie
0x180027349  xor     rax, rsp
0x18002734c  mov     [rsp+58h+var_28], rax
0x180027351  movzx   r14d, dx
0x180027355  mov     rbx, rcx
0x180027358  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002735c  lea     rcx, [rsp+58h+var_38]; this
0x180027361  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180027366  cmp     qword ptr [rbx+28h], 0
0x18002736b  jnz     short loc_180027377
0x18002736d  mov     ebx, 0C00D07F6h
0x180027372  jmp     loc_18002742C
0x180027377  mov     ecx, [rbx+0D0h]
0x18002737d  cmp     r14d, ecx
0x180027380  jb      short loc_18002738C
0x180027382  mov     ebx, 0C00D07F0h
0x180027387  jmp     loc_18002742C
0x18002738c  lea     eax, [r14+1]
0x180027390  cmp     eax, ecx
0x180027392  ja      short loc_1800273B3
0x180027394  xor     esi, esi
0x180027396  mov     edx, r14d
0x180027399  lea     rcx, [rbx+50h]
0x18002739d  call    ?RemoveValue@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(ulong)
0x1800273a2  test    eax, eax
0x1800273a4  js      short loc_1800273B3
0x1800273a6  dec     dword ptr [rbx+0D0h]
0x1800273ac  inc     esi
0x1800273ae  cmp     esi, 1
0x1800273b1  jb      short loc_180027396
0x1800273b3  xor     edi, edi
0x1800273b5  cmp     [rbx+1B0h], edi
0x1800273bb  jbe     short loc_18002742A
0x1800273bd  mov     edx, edi
0x1800273bf  mov     [rsp+58h+var_30], 0
0x1800273c8  lea     rcx, [rbx+0D8h]
0x1800273cf  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x1800273d4  mov     r9, rax
0x1800273d7  lea     r8, [rsp+58h+var_30]
0x1800273dc  lea     rdx, IID_IASFMarkerPriv
0x1800273e3  mov     rcx, [rax]
0x1800273e6  mov     rax, [rcx]
0x1800273e9  mov     rcx, r9
0x1800273ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273f1  test    eax, eax
0x1800273f3  js      short loc_180027420
0x1800273f5  mov     rcx, [rsp+58h+var_30]
0x1800273fa  movzx   edx, r14w
0x1800273fe  mov     rax, [rcx]
0x180027401  mov     rax, [rax+38h]
0x180027405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002740a  mov     rcx, [rsp+58h+var_30]
0x18002740f  test    rcx, rcx
0x180027412  jz      short loc_180027420
0x180027414  mov     rax, [rcx]
0x180027417  mov     rax, [rax+10h]
0x18002741b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027420  inc     edi
0x180027422  cmp     edi, [rbx+1B0h]
0x180027428  jb      short loc_1800273BD
0x18002742a  xor     ebx, ebx
0x18002742c  lea     rcx, [rsp+58h+var_38]; this
0x180027431  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180027436  mov     eax, ebx
0x180027438  mov     rcx, [rsp+58h+var_28]
0x18002743d  xor     rcx, rsp; StackCookie
0x180027440  call    __security_check_cookie
0x180027445  mov     rbx, [rsp+58h+arg_10]
0x18002744a  mov     rbp, [rsp+58h+arg_18]
0x18002744f  add     rsp, 40h
0x180027453  pop     r14
0x180027455  pop     rdi
0x180027456  pop     rsi
0x180027457  retn
```
