# WhitebalanceComponentGetHandler

- ea: `0x1400276e0`
- end: `0x14002795f`
- name: `WhitebalanceComponentGetHandler`
- size: `639`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400051e4`
- `0x140008640`
- `0x140008f80`
- `0x1400274f8`
- `0x1400275d4`
- `0x1400276e0`

## pseudocode

```c
__int64 __fastcall WhitebalanceComponentGetHandler(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v4; // r8
  int NodeInfoAndValidate; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r14
  __int64 v11; // r15
  char v12; // r12
  __int64 v13; // rcx
  int v14; // r8d
  char v16; // [rsp+20h] [rbp-50h]
  int v17; // [rsp+20h] [rbp-50h]
  int v18; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  size_t Sizea; // [rsp+30h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+B0h] [rbp+40h] BYREF
  int v25; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int8 v26; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 v27; // [rsp+C8h] [rbp+58h] BYREF
  unsigned __int16 v28; // [rsp+CAh] [rbp+5Ah]

  LOBYTE(v24) = 0;
  v4 = *(unsigned int *)(a2 + 20);
  LOBYTE(v25) = 0;
  v26 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  if ( (v4 & 0x10000000) == 0 )
  {
    NodeInfoAndValidate = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_dDD(WPP_GLOBAL_Control->AttachedDevice, 15, v4, 1714, -1073741811, v4);
    goto LABEL_23;
  }
  v16 = 5;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, a2, a3, 12, v16, &v24, &v25, &v22, &v21, &v23);
  if ( NodeInfoAndValidate < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_23;
    v8 = 16;
    v9 = 1730;
    goto LABEL_9;
  }
  v10 = v21;
  v11 = v22;
  v12 = v25;
  LODWORD(Size) = 4;
  LOBYTE(v17) = v25;
  NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, 0xC00u, v24, v17, (unsigned __int8 *)&v27, Size, v22, v21);
  if ( NodeInfoAndValidate < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      goto LABEL_23;
    v8 = 17;
    v9 = 1745;
    goto LABEL_9;
  }
  v13 = v23;
  a3[8] = v27;
  a3[11] = v28;
  a3[10] = *(_DWORD *)(v13 + 48);
  v14 = *(_DWORD *)(v13 + 48);
  if ( (v14 & 1) != 0 )
  {
    LODWORD(Sizea) = 1;
    LOBYTE(v18) = v12;
    NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, 0xD00u, v24, v18, &v26, Sizea, v11, v10);
    if ( NodeInfoAndValidate < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        goto LABEL_23;
      v8 = 18;
      v9 = 1768;
LABEL_9:
      WPP_SF_dd(v7->AttachedDevice, v8, WPP_a7e72e311a673739a589ba7821720449_Traceguids, v9, NodeInfoAndValidate);
      goto LABEL_23;
    }
    v14 = 2 - (v26 != 0);
  }
  a3[9] = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_dDDDD(WPP_GLOBAL_Control->AttachedDevice);
LABEL_23:
  *(_DWORD *)(a1 + 48) = NodeInfoAndValidate;
  return (unsigned int)NodeInfoAndValidate;
}

```

## disassembly

```asm
0x1400276e0  push    rbp
0x1400276e2  push    rbx
0x1400276e3  push    rsi
0x1400276e4  push    rdi
0x1400276e5  push    r12
0x1400276e7  push    r14
0x1400276e9  push    r15
0x1400276eb  mov     rbp, rsp
0x1400276ee  sub     rsp, 70h
0x1400276f2  mov     rdi, r8
0x1400276f5  mov     byte ptr [rbp+arg_0], 0
0x1400276f9  mov     r8d, [rdx+14h]
0x1400276fd  mov     rsi, rcx
0x140027700  mov     byte ptr [rbp+arg_8], 0
0x140027704  mov     [rbp+arg_10], 0
0x140027708  mov     [rbp+var_10], 0
0x140027710  mov     [rbp+var_18], 0
0x140027718  mov     [rbp+var_20], 0
0x140027720  bt      r8d, 1Ch
0x140027725  jb      short loc_140027774
0x140027727  mov     ebx, 0C000000Dh
0x14002772c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027733  lea     rax, WPP_GLOBAL_Control
0x14002773a  cmp     rcx, rax
0x14002773d  jz      loc_14002794A
0x140027743  mov     eax, [rcx+2Ch]
0x140027746  test    al, 1
0x140027748  jz      loc_14002794A
0x14002774e  mov     rcx, [rcx+18h]
0x140027752  mov     edx, 0Fh
0x140027757  mov     dword ptr [rsp+70h+var_48], r8d
0x14002775c  mov     r9d, 6B2h
0x140027762  mov     [rsp+70h+var_50], 0C000000Dh
0x14002776a  call    WPP_SF_dDD
0x14002776f  jmp     loc_14002794A
0x140027774  lea     rax, [rbp+var_10]
0x140027778  mov     r9d, 0Ch
0x14002777e  mov     [rsp+70h+var_28], rax
0x140027783  mov     r8, rdi
0x140027786  lea     rax, [rbp+var_20]
0x14002778a  mov     [rsp+70h+var_30], rax
0x14002778f  lea     rax, [rbp+var_18]
0x140027793  mov     [rsp+70h+var_38], rax
0x140027798  lea     rax, [rbp+arg_8]
0x14002779c  mov     [rsp+70h+Size], rax
0x1400277a1  lea     rax, [rbp+arg_0]
0x1400277a5  mov     [rsp+70h+var_48], rax
0x1400277aa  mov     byte ptr [rsp+70h+var_50], 5
0x1400277af  call    GetNodeInfoAndValidate
0x1400277b4  mov     ebx, eax
0x1400277b6  test    eax, eax
0x1400277b8  jns     short loc_140027801
0x1400277ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400277c1  lea     rax, WPP_GLOBAL_Control
0x1400277c8  cmp     rcx, rax
0x1400277cb  jz      loc_14002794A
0x1400277d1  mov     edx, [rcx+2Ch]
0x1400277d4  test    dl, 2
0x1400277d7  jz      loc_14002794A
0x1400277dd  mov     edx, 10h
0x1400277e2  mov     r9d, 6C2h
0x1400277e8  mov     rcx, [rcx+18h]
0x1400277ec  lea     r8, WPP_a7e72e311a673739a589ba7821720449_Traceguids
0x1400277f3  mov     [rsp+70h+var_50], ebx
0x1400277f7  call    WPP_SF_dd
0x1400277fc  jmp     loc_14002794A
0x140027801  mov     r14, [rbp+var_20]
0x140027805  lea     rax, [rbp+arg_18]
0x140027809  mov     r15, [rbp+var_18]
0x14002780d  mov     r8d, 0C00h; int
0x140027813  mov     r12b, byte ptr [rbp+arg_8]
0x140027817  mov     dl, 81h; int
0x140027819  mov     r9b, byte ptr [rbp+arg_0]; int
0x14002781d  mov     cl, 0A1h; int
0x14002781f  mov     [rsp+70h+var_30], r14; __int64
0x140027824  mov     [rsp+70h+var_38], r15; __int64
0x140027829  mov     dword ptr [rsp+70h+Size], 4; Size
0x140027831  mov     [rsp+70h+var_48], rax; void *
0x140027836  mov     byte ptr [rsp+70h+var_50], r12b; int
0x14002783b  call    SubmitControlRequest
0x140027840  mov     ebx, eax
0x140027842  test    eax, eax
0x140027844  jns     short loc_140027878
0x140027846  mov     rcx, cs:WPP_GLOBAL_Control
0x14002784d  lea     rax, WPP_GLOBAL_Control
0x140027854  cmp     rcx, rax
0x140027857  jz      loc_14002794A
0x14002785d  mov     eax, [rcx+2Ch]
0x140027860  test    al, 2
0x140027862  jz      loc_14002794A
0x140027868  mov     edx, 11h
0x14002786d  mov     r9d, 6D1h
0x140027873  jmp     loc_1400277E8
0x140027878  movzx   eax, [rbp+arg_18]
0x14002787c  mov     rcx, [rbp+var_10]
0x140027880  mov     [rdi+20h], eax
0x140027883  movzx   eax, [rbp+arg_1A]
0x140027887  mov     [rdi+2Ch], eax
0x14002788a  mov     eax, [rcx+30h]
0x14002788d  mov     [rdi+28h], eax
0x140027890  mov     r8d, [rcx+30h]
0x140027894  test    r8b, 1
0x140027898  jz      short loc_140027909
0x14002789a  mov     r9b, byte ptr [rbp+arg_0]; int
0x14002789e  lea     rax, [rbp+arg_10]
0x1400278a2  mov     [rsp+70h+var_30], r14; __int64
0x1400278a7  mov     r8d, 0D00h; int
0x1400278ad  mov     [rsp+70h+var_38], r15; __int64
0x1400278b2  mov     dl, 81h; int
0x1400278b4  mov     dword ptr [rsp+70h+Size], 1; Size
0x1400278bc  mov     cl, 0A1h; int
0x1400278be  mov     [rsp+70h+var_48], rax; void *
0x1400278c3  mov     byte ptr [rsp+70h+var_50], r12b; int
0x1400278c8  call    SubmitControlRequest
0x1400278cd  mov     ebx, eax
0x1400278cf  test    eax, eax
0x1400278d1  jns     short loc_1400278FD
0x1400278d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400278da  lea     rax, WPP_GLOBAL_Control
0x1400278e1  cmp     rcx, rax
0x1400278e4  jz      short loc_14002794A
0x1400278e6  mov     eax, [rcx+2Ch]
0x1400278e9  test    al, 2
0x1400278eb  jz      short loc_14002794A
0x1400278ed  mov     edx, 12h
0x1400278f2  mov     r9d, 6E8h
0x1400278f8  jmp     loc_1400277E8
0x1400278fd  mov     al, [rbp+arg_10]
0x140027900  neg     al
0x140027902  sbb     r8d, r8d
0x140027905  add     r8d, 2
0x140027909  mov     [rdi+24h], r8d
0x14002790d  lea     rax, WPP_GLOBAL_Control
0x140027914  mov     rcx, cs:WPP_GLOBAL_Control
0x14002791b  cmp     rcx, rax
0x14002791e  jz      short loc_14002794A
0x140027920  mov     eax, [rcx+2Ch]
0x140027923  test    al, 8
0x140027925  jz      short loc_14002794A
0x140027927  mov     eax, [rdi+28h]
0x14002792a  mov     rcx, [rcx+18h]
0x14002792e  mov     dword ptr [rsp+70h+var_38], eax
0x140027932  mov     eax, [rdi+2Ch]
0x140027935  mov     dword ptr [rsp+70h+Size], r8d
0x14002793a  mov     dword ptr [rsp+70h+var_48], eax
0x14002793e  mov     eax, [rdi+20h]
0x140027941  mov     [rsp+70h+var_50], eax
0x140027945  call    WPP_SF_dDDDD
0x14002794a  mov     [rsi+30h], ebx
0x14002794d  mov     eax, ebx
0x14002794f  add     rsp, 70h
0x140027953  pop     r15
0x140027955  pop     r14
0x140027957  pop     r12
0x140027959  pop     rdi
0x14002795a  pop     rsi
0x14002795b  pop     rbx
0x14002795c  pop     rbp
0x14002795d  retn
```
