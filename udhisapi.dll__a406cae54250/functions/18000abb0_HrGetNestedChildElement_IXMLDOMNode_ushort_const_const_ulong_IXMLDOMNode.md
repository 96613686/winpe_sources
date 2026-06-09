# HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)

- ea: `0x18000abb0`
- end: `0x18000ad4e`
- name: `?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *const *, __int64, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005b68`

## callees

- `0x1800024c4`
- `0x1800038ec`
- `0x180009bcc`
- `0x18000a9b8`
- `0x18000abb0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall HrGetNestedChildElement(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *const *a2,
        __int64 a3,
        struct IXMLDOMNode **a4)
{
  struct IXMLDOMNode *v6; // rdi
  __int64 v7; // rsi
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  char *v9; // rbp
  int ChildElement; // ebx
  _QWORD *v11; // rcx
  struct IXMLDOMNode *v13; // [rsp+60h] [rbp+8h] BYREF
  struct IXMLDOMNode *v14; // [rsp+78h] [rbp+20h] BYREF

  v6 = a1;
  ((void (__fastcall *)(struct IXMLDOMNode *))a1->lpVtbl->AddRef)(a1);
  v7 = 0;
  while ( 1 )
  {
    lpVtbl = v6->lpVtbl;
    v9 = (char *)a2[v7];
    v14 = 0;
    v13 = 0;
    ChildElement = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))lpVtbl->get_firstChild)(
                     v6,
                     &v13);
    if ( ChildElement < 0 )
      break;
    ChildElement = HrGetChildElement(v13, v9, &v14);
    if ( v13 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
      v13 = 0;
    }
    if ( ChildElement < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    if ( ChildElement == 1 )
      goto LABEL_17;
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v6 = v14;
    v7 = (unsigned int)(v7 + 1);
    if ( (_DWORD)v7 )
    {
      *a4 = v14;
      return (unsigned int)ChildElement;
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)"HrGetFirstChildElement - get_firstChild",
      ChildElement);
    v11 = WPP_GLOBAL_Control;
  }
  v13 = 0;
LABEL_14:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    WPP_SF_Sd(v11[2], 33, (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, (_DWORD)v9, ChildElement);
LABEL_17:
  ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  *a4 = 0;
  if ( ChildElement < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)ChildElement);
  }
  return (unsigned int)ChildElement;
}

```

## disassembly

```asm
0x18000abb0  mov     [rsp+arg_8], rbx
0x18000abb5  push    rbp
0x18000abb6  push    rsi
0x18000abb7  push    rdi
0x18000abb8  push    r14
0x18000abba  push    r15
0x18000abbc  sub     rsp, 30h
0x18000abc0  mov     rax, [rcx]
0x18000abc3  mov     r14, r9
0x18000abc6  mov     r15, rdx
0x18000abc9  mov     rdi, rcx
0x18000abcc  mov     rax, [rax+8]
0x18000abd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abd5  xor     esi, esi
0x18000abd7  mov     rax, [rdi]
0x18000abda  lea     rdx, [rsp+58h+arg_0]
0x18000abdf  mov     rbp, [r15+rsi*8]
0x18000abe3  mov     rcx, rdi
0x18000abe6  mov     [rsp+58h+arg_18], 0
0x18000abef  mov     [rsp+58h+arg_0], 0
0x18000abf8  mov     rax, [rax+68h]
0x18000abfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac01  mov     ebx, eax
0x18000ac03  lea     rax, WPP_GLOBAL_Control
0x18000ac0a  test    ebx, ebx
0x18000ac0c  js      short loc_18000AC7E
0x18000ac0e  mov     rcx, [rsp+58h+arg_0]; struct IXMLDOMNode *
0x18000ac13  lea     r8, [rsp+58h+arg_18]; struct IXMLDOMNode **
0x18000ac18  mov     rdx, rbp; unsigned __int16 *
0x18000ac1b  call    ?HrGetChildElement@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; HrGetChildElement(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000ac20  mov     ebx, eax
0x18000ac22  mov     rcx, [rsp+58h+arg_0]
0x18000ac27  test    rcx, rcx
0x18000ac2a  jz      short loc_18000AC41
0x18000ac2c  mov     rax, [rcx]
0x18000ac2f  mov     rax, [rax+10h]
0x18000ac33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac38  mov     [rsp+58h+arg_0], 0
0x18000ac41  test    ebx, ebx
0x18000ac43  js      short loc_18000AC75
0x18000ac45  cmp     ebx, 1
0x18000ac48  jz      loc_18000ACF0
0x18000ac4e  mov     rax, [rdi]
0x18000ac51  mov     rcx, rdi
0x18000ac54  mov     rax, [rax+10h]
0x18000ac58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac5d  mov     rdi, [rsp+58h+arg_18]
0x18000ac62  inc     esi
0x18000ac64  cmp     esi, 1
0x18000ac67  jb      loc_18000ABD7
0x18000ac6d  mov     [r14], rdi
0x18000ac70  jmp     loc_18000AD3B
0x18000ac75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac7c  jmp     short loc_18000ACC0
0x18000ac7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac85  cmp     rcx, rax
0x18000ac88  jz      short loc_18000ACB7
0x18000ac8a  test    byte ptr [rcx+1Ch], 1
0x18000ac8e  jz      short loc_18000ACB7
0x18000ac90  mov     rcx, [rcx+10h]
0x18000ac94  lea     r9, aHrgetfirstchil; "HrGetFirstChildElement - get_firstChild"
0x18000ac9b  mov     edx, 20h ; ' '
0x18000aca0  mov     [rsp+58h+var_38], ebx
0x18000aca4  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000acab  call    WPP_SF_sd
0x18000acb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acb7  mov     [rsp+58h+arg_0], 0
0x18000acc0  lea     rsi, WPP_GLOBAL_Control
0x18000acc7  cmp     rcx, rsi
0x18000acca  jz      short loc_18000ACF7
0x18000accc  test    byte ptr [rcx+1Ch], 1
0x18000acd0  jz      short loc_18000ACF7
0x18000acd2  mov     rcx, [rcx+10h]
0x18000acd6  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000acdd  mov     edx, 21h ; '!'
0x18000ace2  mov     [rsp+58h+var_38], ebx
0x18000ace6  mov     r9, rbp
0x18000ace9  call    WPP_SF_Sd
0x18000acee  jmp     short loc_18000ACF7
0x18000acf0  lea     rsi, WPP_GLOBAL_Control
0x18000acf7  mov     rax, [rdi]
0x18000acfa  mov     rcx, rdi
0x18000acfd  mov     rax, [rax+10h]
0x18000ad01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad06  mov     qword ptr [r14], 0
0x18000ad0d  test    ebx, ebx
0x18000ad0f  jns     short loc_18000AD3B
0x18000ad11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad18  cmp     rcx, rsi
0x18000ad1b  jz      short loc_18000AD3B
0x18000ad1d  test    byte ptr [rcx+1Ch], 1
0x18000ad21  jz      short loc_18000AD3B
0x18000ad23  mov     rcx, [rcx+10h]
0x18000ad27  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000ad2e  mov     edx, 2Ch ; ','
0x18000ad33  mov     r9d, ebx
0x18000ad36  call    WPP_SF_d
0x18000ad3b  mov     eax, ebx
0x18000ad3d  mov     rbx, [rsp+58h+arg_8]
0x18000ad42  add     rsp, 30h
0x18000ad46  pop     r15
0x18000ad48  pop     r14
0x18000ad4a  pop     rdi
0x18000ad4b  pop     rsi
0x18000ad4c  pop     rbp
0x18000ad4d  retn
```
