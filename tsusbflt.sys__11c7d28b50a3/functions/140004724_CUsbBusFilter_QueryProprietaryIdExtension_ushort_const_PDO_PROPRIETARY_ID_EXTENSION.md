# CUsbBusFilter::QueryProprietaryIdExtension(ushort const *,_PDO_PROPRIETARY_ID_EXTENSION * *)

- ea: `0x140004724`
- end: `0x1400048cb`
- name: `?QueryProprietaryIdExtension@CUsbBusFilter@@AEAAJPEBGPEAPEAU_PDO_PROPRIETARY_ID_EXTENSION@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CUsbBusFilter *__hidden this, const unsigned __int16 *, struct _PDO_PROPRIETARY_ID_EXTENSION **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140002bc4`
- `0x140003f90`

## callees

- `0x140004724`
- `0x140004f8c`
- `0x1400050c8`
- `0x14000aa30`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::QueryProprietaryIdExtension(
        CUsbBusFilter *this,
        const unsigned __int16 *a2,
        struct _PDO_PROPRIETARY_ID_EXTENSION **a3)
{
  __int64 v6; // rbx
  unsigned int v7; // edi
  unsigned int v8; // esi
  __int64 v9; // r8
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  int v12; // edx
  int v13; // ecx
  __int64 result; // rax
  unsigned int v15; // edi
  unsigned int v16; // esi
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r8d

  v6 = 0;
  v7 = 0;
  v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         *((_QWORD *)this + 3));
  if ( !v8 )
    goto LABEL_9;
  do
  {
    v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            *((_QWORD *)this + 3),
            v7);
    v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           v10,
           off_14000F150);
    v11 = a2;
    v9 = v6 + 104 + *(_QWORD *)(v6 + 96) - (_QWORD)a2;
    do
    {
      v12 = *(const unsigned __int16 *)((char *)v11 + v9);
      v13 = *v11 - v12;
      if ( v13 )
        break;
      ++v11;
    }
    while ( v12 );
    if ( !v13 )
      break;
    v6 = 0;
    ++v7;
  }
  while ( v7 < v8 );
  result = 0;
  if ( !v6 )
  {
LABEL_9:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 22, v9, a2);
    v15 = 0;
    v16 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            *((_QWORD *)this + 3));
    if ( v16 )
    {
      do
      {
        v17 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                *((_QWORD *)this + 3),
                v15);
        v18 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                v17,
                off_14000F150);
        v6 = v18;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_qS(
            WPP_GLOBAL_Control->AttachedDevice,
            v18 + *(_DWORD *)(v18 + 96) + 104,
            v19,
            *(_QWORD *)(v18 + 8),
            v18 + *(_QWORD *)(v18 + 96) + 104LL);
        ++v15;
      }
      while ( v15 < v16 );
    }
    result = 3221226021LL;
  }
  *a3 = (struct _PDO_PROPRIETARY_ID_EXTENSION *)v6;
  return result;
}

```

## disassembly

```asm
0x140004724  push    rbx
0x140004726  push    rbp
0x140004727  push    rsi
0x140004728  push    rdi
0x140004729  push    r12
0x14000472b  push    r14
0x14000472d  push    r15
0x14000472f  sub     rsp, 30h
0x140004733  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000473a  mov     r14, rdx
0x14000473d  mov     rdx, [rcx+18h]
0x140004741  mov     rbp, rcx
0x140004744  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000474b  mov     r15, r8
0x14000474e  mov     rax, [rax+70h]
0x140004752  call    _guard_dispatch_icall
0x140004757  xor     ebx, ebx
0x140004759  xor     edi, edi
0x14000475b  mov     esi, eax
0x14000475d  test    eax, eax
0x14000475f  jz      loc_1400047E9
0x140004765  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000476c  mov     r8d, edi
0x14000476f  mov     rdx, [rbp+18h]
0x140004773  mov     rax, [rcx+90h]
0x14000477a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004781  call    _guard_dispatch_icall
0x140004786  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000478d  mov     rdx, rax
0x140004790  mov     r8, cs:off_14000F150
0x140004797  mov     rax, [rcx+650h]
0x14000479e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400047a5  call    _guard_dispatch_icall
0x1400047aa  mov     rbx, rax
0x1400047ad  mov     r8, [rax+60h]
0x1400047b1  add     rax, 68h ; 'h'
0x1400047b5  add     r8, rax
0x1400047b8  mov     rax, r14
0x1400047bb  sub     r8, r14
0x1400047be  movzx   ecx, word ptr [rax]
0x1400047c1  movzx   edx, word ptr [rax+r8]
0x1400047c6  sub     ecx, edx
0x1400047c8  jnz     short loc_1400047D2
0x1400047ca  add     rax, 2
0x1400047ce  test    edx, edx
0x1400047d0  jnz     short loc_1400047BE
0x1400047d2  test    ecx, ecx
0x1400047d4  jz      short loc_1400047DE
0x1400047d6  xor     ebx, ebx
0x1400047d8  inc     edi
0x1400047da  cmp     edi, esi
0x1400047dc  jb      short loc_140004765
0x1400047de  xor     eax, eax
0x1400047e0  test    rbx, rbx
0x1400047e3  jnz     loc_1400048B8
0x1400047e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047f0  lea     r12, WPP_GLOBAL_Control
0x1400047f7  cmp     rcx, r12
0x1400047fa  jz      short loc_140004813
0x1400047fc  cmp     byte ptr [rcx+29h], 2
0x140004800  jb      short loc_140004813
0x140004802  mov     rcx, [rcx+18h]
0x140004806  mov     edx, 16h
0x14000480b  mov     r9, r14
0x14000480e  call    WPP_SF_S
0x140004813  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000481a  mov     rdx, [rbp+18h]
0x14000481e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004825  mov     rax, [rax+70h]
0x140004829  call    _guard_dispatch_icall
0x14000482e  xor     edi, edi
0x140004830  mov     esi, eax
0x140004832  test    eax, eax
0x140004834  jz      short loc_1400048B3
0x140004836  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000483d  mov     r8d, edi
0x140004840  mov     rdx, [rbp+18h]
0x140004844  mov     rax, [rcx+90h]
0x14000484b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004852  call    _guard_dispatch_icall
0x140004857  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000485e  mov     rdx, rax
0x140004861  mov     r8, cs:off_14000F150
0x140004868  mov     rax, [rcx+650h]
0x14000486f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004876  call    _guard_dispatch_icall
0x14000487b  mov     rbx, rax
0x14000487e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004885  cmp     rcx, r12
0x140004888  jz      short loc_1400048AD
0x14000488a  cmp     byte ptr [rcx+29h], 2
0x14000488e  jb      short loc_1400048AD
0x140004890  mov     rdx, [rax+60h]
0x140004894  mov     r9, [rax+8]
0x140004898  add     rdx, 68h ; 'h'
0x14000489c  mov     rcx, [rcx+18h]
0x1400048a0  add     rdx, rax
0x1400048a3  mov     [rsp+68h+var_48], rdx
0x1400048a8  call    WPP_SF_qS
0x1400048ad  inc     edi
0x1400048af  cmp     edi, esi
0x1400048b1  jb      short loc_140004836
0x1400048b3  mov     eax, 0C0000225h
0x1400048b8  mov     [r15], rbx
0x1400048bb  add     rsp, 30h
0x1400048bf  pop     r15
0x1400048c1  pop     r14
0x1400048c3  pop     r12
0x1400048c5  pop     rdi
0x1400048c6  pop     rsi
0x1400048c7  pop     rbp
0x1400048c8  pop     rbx
0x1400048c9  retn
```
