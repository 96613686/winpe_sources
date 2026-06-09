# IASCollection::Initialize(_ITEMTYPE,ISdoCollection *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)

- ea: `0x180030814`
- end: `0x1800308e1`
- name: `?Initialize@IASCollection@@QEAAJW4_ITEMTYPE@@PEAUISdoCollection@@PEAUISdo@@PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z`
- size: `205`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002f458`
- `0x180035214`
- `0x180035480`
- `0x180040af0`

## callees

- `0x18002cd00`
- `0x18002d278`
- `0x180030644`
- `0x180030814`
- `0x180042a80`

## string_xrefs

- `0x1800308a1`: `CreateNewEnumerator() failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASCollection::Initialize(
        __int64 a1,
        int a2,
        struct IUnknown *a3,
        struct IUnknown *a4,
        struct IUnknown *a5,
        struct IUnknown *a6)
{
  struct IUnknown **v7; // rcx
  int NewEnumerator; // ebx

  *(_DWORD *)(a1 + 8) = a2;
  v7 = (struct IUnknown **)(a1 + 16);
  if ( *v7 != a3 )
    ATL::AtlComPtrAssign(v7, a3);
  if ( *(struct IUnknown **)(a1 + 24) != a4 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 24), a4);
  if ( *(struct IUnknown **)(a1 + 32) != a5 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 32), a5);
  if ( *(struct IUnknown **)(a1 + 40) != a6 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 40), a6);
  NewEnumerator = IASCollection::CreateNewEnumerator((IASCollection *)a1);
  if ( NewEnumerator < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("CreateNewEnumerator() failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_c2f236718121324f7e73e45b18920f9d_Traceguids,
      (unsigned int)"NPSSDO",
      NewEnumerator);
  }
  return (unsigned int)NewEnumerator;
}

```

## disassembly

```asm
0x180030814  mov     [rsp+arg_0], rbx
0x180030819  push    rdi
0x18003081a  sub     rsp, 30h
0x18003081e  mov     [rcx+8], edx
0x180030821  mov     rbx, rcx
0x180030824  add     rcx, 10h; struct IUnknown **
0x180030828  mov     rdi, r9
0x18003082b  cmp     [rcx], r8
0x18003082e  jz      short loc_180030838
0x180030830  mov     rdx, r8; struct IUnknown *
0x180030833  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180030838  lea     rcx, [rbx+18h]; struct IUnknown **
0x18003083c  cmp     [rcx], rdi
0x18003083f  jz      short loc_180030849
0x180030841  mov     rdx, rdi; struct IUnknown *
0x180030844  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180030849  mov     rdx, [rsp+38h+arg_20]; struct IUnknown *
0x18003084e  lea     rcx, [rbx+20h]; struct IUnknown **
0x180030852  cmp     [rcx], rdx
0x180030855  jz      short loc_18003085C
0x180030857  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003085c  mov     rdx, [rsp+38h+arg_28]; struct IUnknown *
0x180030861  lea     rcx, [rbx+28h]; struct IUnknown **
0x180030865  cmp     [rcx], rdx
0x180030868  jz      short loc_18003086F
0x18003086a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003086f  mov     rcx, rbx; this
0x180030872  call    ?CreateNewEnumerator@IASCollection@@QEAAJXZ; IASCollection::CreateNewEnumerator(void)
0x180030877  mov     ebx, eax
0x180030879  test    eax, eax
0x18003087b  jns     short loc_1800308D4
0x18003087d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030884  lea     rax, WPP_GLOBAL_Control
0x18003088b  cmp     rcx, rax
0x18003088e  jz      short loc_1800308D4
0x180030890  cmp     byte ptr [rcx+19h], 2
0x180030894  jb      short loc_1800308D4
0x180030896  test    dword ptr [rcx+1Ch], 400h
0x18003089d  jz      short loc_1800308D4
0x18003089f  mov     edx, ebx
0x1800308a1  lea     rcx, aCreatenewenume; "CreateNewEnumerator() failed with 0x%x"
0x1800308a8  call    WppDbgPrint
0x1800308ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308b4  lea     r9, aNpssdo; "NPSSDO"
0x1800308bb  mov     edx, 0Dh
0x1800308c0  mov     [rsp+38h+var_18], ebx
0x1800308c4  lea     r8, WPP_c2f236718121324f7e73e45b18920f9d_Traceguids
0x1800308cb  mov     rcx, [rcx+10h]
0x1800308cf  call    WPP_SF_sd
0x1800308d4  mov     eax, ebx
0x1800308d6  mov     rbx, [rsp+38h+arg_0]
0x1800308db  add     rsp, 30h
0x1800308df  pop     rdi
0x1800308e0  retn
```
