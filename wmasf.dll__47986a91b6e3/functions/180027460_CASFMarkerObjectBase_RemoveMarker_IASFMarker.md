# CASFMarkerObjectBase::RemoveMarker(IASFMarker *)

- ea: `0x180027460`
- end: `0x1800275b4`
- name: `?RemoveMarker@CASFMarkerObjectBase@@UEAAJPEAUIASFMarker@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CASFMarkerObjectBase *__hidden this, struct IASFMarker *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800266c0`
- `0x180027460`
- `0x1800275bc`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarkerObjectBase::RemoveMarker(struct IWMSCriticalSection **this, struct IASFMarker *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  char *v6; // rbx
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rax
  __int64 v8; // rax
  int v9; // esi
  _BYTE v11[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v11, this[4]);
  if ( this[5] )
  {
    v5 = 0;
    v6 = (char *)(this + 27);
    while ( 1 )
    {
      if ( v5 >= *((_DWORD *)v6 + 54) )
      {
        v4 = -1072887824;
        goto LABEL_18;
      }
      if ( a2 == (struct IASFMarker *)CTDynArray<IASFMarker *,20>::operator[](v6, v5) )
        break;
      ++v5;
    }
    v12 = 0;
    v7 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))CTDynArray<IASFMarker *,20>::operator[](v6, v5);
    if ( (**v7)(v7, &IID_IASFMarkerPriv, &v12) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v12 = 0;
      }
    }
    if ( CTDynArray<IASFMarker *,20>::operator[](v6, v5) )
    {
      v8 = CTDynArray<IASFMarker *,20>::operator[](v6, v5);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( v5 + 1 <= *((_DWORD *)v6 + 54) )
    {
      v9 = 0;
      do
      {
        if ( (int)CTSparseBlock<unsigned long,IASFMarker *,20,0>::RemoveValue(v6, v5) < 0 )
          break;
        --*((_DWORD *)v6 + 54);
        ++v9;
      }
      while ( !v9 );
    }
    v4 = 0;
  }
  else
  {
    v4 = -1072887818;
  }
LABEL_18:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v11);
  return v4;
}

```

## disassembly

```asm
0x180027460  mov     [rsp+arg_8], rbx
0x180027465  mov     [rsp+arg_10], rsi
0x18002746a  push    rdi
0x18002746b  sub     rsp, 40h
0x18002746f  mov     rax, cs:__security_cookie
0x180027476  xor     rax, rsp
0x180027479  mov     [rsp+48h+var_18], rax
0x18002747e  mov     rsi, rdx
0x180027481  mov     rbx, rcx
0x180027484  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180027488  lea     rcx, [rsp+48h+var_28]; this
0x18002748d  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180027492  cmp     qword ptr [rbx+28h], 0
0x180027497  jnz     short loc_1800274A3
0x180027499  mov     ebx, 0C00D07F6h
0x18002749e  jmp     loc_18002758B
0x1800274a3  xor     edi, edi
0x1800274a5  add     rbx, 0D8h
0x1800274ac  cmp     edi, [rbx+0D8h]
0x1800274b2  jnb     loc_180027586
0x1800274b8  mov     edx, edi
0x1800274ba  mov     rcx, rbx
0x1800274bd  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x1800274c2  cmp     rsi, rax
0x1800274c5  jz      short loc_1800274CB
0x1800274c7  inc     edi
0x1800274c9  jmp     short loc_1800274AC
0x1800274cb  mov     edx, edi
0x1800274cd  mov     [rsp+48h+var_20], 0
0x1800274d6  mov     rcx, rbx
0x1800274d9  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x1800274de  mov     r9, rax
0x1800274e1  lea     r8, [rsp+48h+var_20]
0x1800274e6  lea     rdx, IID_IASFMarkerPriv
0x1800274ed  mov     rcx, [rax]
0x1800274f0  mov     rax, [rcx]
0x1800274f3  mov     rcx, r9
0x1800274f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274fb  test    eax, eax
0x1800274fd  js      short loc_18002752F
0x1800274ff  mov     rcx, [rsp+48h+var_20]
0x180027504  mov     rax, [rcx]
0x180027507  mov     rax, [rax+20h]
0x18002750b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027510  mov     rcx, [rsp+48h+var_20]
0x180027515  test    rcx, rcx
0x180027518  jz      short loc_18002752F
0x18002751a  mov     rax, [rcx]
0x18002751d  mov     rax, [rax+10h]
0x180027521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027526  mov     [rsp+48h+var_20], 0
0x18002752f  mov     edx, edi
0x180027531  mov     rcx, rbx
0x180027534  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x180027539  test    rax, rax
0x18002753c  jz      short loc_18002755A
0x18002753e  mov     edx, edi
0x180027540  mov     rcx, rbx
0x180027543  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x180027548  mov     rdx, rax
0x18002754b  mov     rcx, [rax]
0x18002754e  mov     rax, [rcx+10h]
0x180027552  mov     rcx, rdx
0x180027555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002755a  lea     eax, [rdi+1]
0x18002755d  cmp     eax, [rbx+0D8h]
0x180027563  ja      short loc_180027582
0x180027565  xor     esi, esi
0x180027567  mov     edx, edi
0x180027569  mov     rcx, rbx
0x18002756c  call    ?RemoveValue@?$CTSparseBlock@KPEAUIASFMarker@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,IASFMarker *,20,0>::RemoveValue(ulong)
0x180027571  test    eax, eax
0x180027573  js      short loc_180027582
0x180027575  dec     dword ptr [rbx+0D8h]
0x18002757b  inc     esi
0x18002757d  cmp     esi, 1
0x180027580  jb      short loc_180027567
0x180027582  xor     ebx, ebx
0x180027584  jmp     short loc_18002758B
0x180027586  mov     ebx, 0C00D07F0h
0x18002758b  lea     rcx, [rsp+48h+var_28]; this
0x180027590  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180027595  mov     eax, ebx
0x180027597  mov     rcx, [rsp+48h+var_18]
0x18002759c  xor     rcx, rsp; StackCookie
0x18002759f  call    __security_check_cookie
0x1800275a4  mov     rbx, [rsp+48h+arg_8]
0x1800275a9  mov     rsi, [rsp+48h+arg_10]
0x1800275ae  add     rsp, 40h
0x1800275b2  pop     rdi
0x1800275b3  retn
```
