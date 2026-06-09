# SdpIsSubDirectory(ushort const *,ushort const *,int *)

- ea: `0x18002758c`
- end: `0x180027785`
- name: `?SdpIsSubDirectory@@YAJPEBG0PEAH@Z`
- size: `505`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000615c`
- `0x1800101cc`
- `0x18001dc28`
- `0x180026958`

## callees

- `0x1800012a4`
- `0x180026fa0`
- `0x18002708c`
- `0x18002758c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800276fa`
- `msvcrt!_wcsnicmp` at `0x1800276fa`

## string_xrefs

- `0x1800275cc`: `SdpIsSubDirectory`
- `0x180027618`: `SdpIsSubDirectory`
- `0x180027742`: `SdpIsSubDirectory`

## pseudocode

```c
__int64 __fastcall SdpIsSubDirectory(const unsigned __int16 *a1, const unsigned __int16 *a2, int *a3)
{
  wchar_t *v5; // rdi
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  int FullPath; // eax
  wchar_t *v9; // rbp
  int v10; // r9d
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // r9d
  unsigned int v14; // r8d
  wchar_t *v15; // rax
  __int64 v16; // r8
  size_t v17; // rsi
  __int64 v18; // rcx
  wchar_t *v19; // rax
  wchar_t *String2; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp+20h] BYREF

  String1 = 0;
  String2 = 0;
  v5 = 0;
  if ( !a1 )
  {
    v6 = 1956;
LABEL_3:
    v7 = -2147024809;
    SdpDebugTrace(1u, L"SdpIsSubDirectory", v6, -2147024809);
    return v7;
  }
  if ( !a2 )
  {
    v6 = 1957;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 1958;
    goto LABEL_3;
  }
  FullPath = SdpGetFullPath(a1, &String1, 0);
  v9 = String1;
  v7 = FullPath;
  if ( FullPath >= 0 )
  {
    v12 = SdpGetFullPath(a2, &String2, 0);
    v7 = v12;
    if ( v12 >= 0 )
    {
      if ( v9 )
      {
        v15 = v9;
        v16 = 260;
        do
        {
          if ( !*v15 )
            break;
          ++v15;
          --v16;
        }
        while ( v16 );
        v7 = v16 == 0 ? 0x80070057 : 0;
        v17 = (260 - v16) & -(__int64)(v16 != 0);
        if ( v16 )
        {
          v5 = String2;
          if ( String2 )
          {
            v18 = 260;
            v19 = String2;
            do
            {
              if ( !*v19 )
                break;
              ++v19;
              --v18;
            }
            while ( v18 );
            v7 = v18 == 0 ? 0x80070057 : 0;
            if ( v18 )
            {
              *a3 = ((260 - v18) & ((unsigned __int128)-(__int128)(unsigned __int64)v18 >> 64)) > v17
                 && !_wcsnicmp(v9, String2, v17)
                 && (v9[v17 - 1] == 92 || v5[v17] == 92 && v5[v17 + 1]);
              goto LABEL_35;
            }
          }
          else
          {
            v7 = -2147024809;
          }
          v10 = -2147024809;
          v11 = 1970;
          goto LABEL_10;
        }
      }
      else
      {
        v7 = -2147024809;
      }
      v13 = v7;
      v14 = 1967;
    }
    else
    {
      v13 = v12;
      v14 = 1964;
    }
    SdpDebugTrace(1u, L"SdpIsSubDirectory", v14, v13);
    v5 = String2;
    goto LABEL_35;
  }
  v10 = FullPath;
  v11 = 1961;
LABEL_10:
  SdpDebugTrace(1u, L"SdpIsSubDirectory", v11, v10);
LABEL_35:
  if ( v9 )
    operator delete(v9);
  if ( v5 )
    operator delete(v5);
  return v7;
}

```

## disassembly

```asm
0x18002758c  mov     [rsp+arg_8], rbx
0x180027591  push    rbp
0x180027592  push    rsi
0x180027593  push    rdi
0x180027594  push    r14
0x180027596  push    r15
0x180027598  sub     rsp, 20h
0x18002759c  xor     r15d, r15d
0x18002759f  mov     r14, r8
0x1800275a2  mov     [rsp+48h+String1], r15
0x1800275a7  mov     rsi, rdx
0x1800275aa  mov     [rsp+48h+String2], r15
0x1800275af  mov     edi, r15d
0x1800275b2  test    rcx, rcx
0x1800275b5  jnz     short loc_1800275DD
0x1800275b7  mov     r8d, 7A4h; int
0x1800275bd  mov     edx, 80070057h
0x1800275c2  mov     ecx, 1; Level
0x1800275c7  mov     ebx, edx
0x1800275c9  mov     r9d, edx; int
0x1800275cc  lea     rdx, aSdpissubdirect; "SdpIsSubDirectory"
0x1800275d3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800275d8  jmp     loc_180027772
0x1800275dd  test    rsi, rsi
0x1800275e0  jnz     short loc_1800275EA
0x1800275e2  mov     r8d, 7A5h
0x1800275e8  jmp     short loc_1800275BD
0x1800275ea  test    r14, r14
0x1800275ed  jnz     short loc_1800275F7
0x1800275ef  mov     r8d, 7A6h
0x1800275f5  jmp     short loc_1800275BD
0x1800275f7  xor     r8d, r8d; unsigned __int16 **
0x1800275fa  lea     rdx, [rsp+48h+String1]; unsigned __int16 **
0x1800275ff  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x180027604  mov     rbp, [rsp+48h+String1]
0x180027609  mov     ebx, eax
0x18002760b  test    eax, eax
0x18002760d  jns     short loc_18002762E
0x18002760f  mov     r9d, eax; int
0x180027612  mov     r8d, 7A9h; int
0x180027618  lea     rdx, aSdpissubdirect; "SdpIsSubDirectory"
0x18002761f  mov     ecx, 1; Level
0x180027624  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027629  jmp     loc_180027758
0x18002762e  xor     r8d, r8d; unsigned __int16 **
0x180027631  lea     rdx, [rsp+48h+String2]; unsigned __int16 **
0x180027636  mov     rcx, rsi; unsigned __int16 *
0x180027639  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x18002763e  mov     ebx, eax
0x180027640  test    eax, eax
0x180027642  jns     short loc_180027652
0x180027644  mov     r9d, eax
0x180027647  mov     r8d, 7ACh
0x18002764d  jmp     loc_180027742
0x180027652  test    rbp, rbp
0x180027655  jz      loc_180027734
0x18002765b  mov     r9d, 104h
0x180027661  mov     rax, rbp
0x180027664  mov     r8d, r9d
0x180027667  cmp     [rax], r15w
0x18002766b  jz      short loc_180027677
0x18002766d  add     rax, 2
0x180027671  sub     r8, 1
0x180027675  jnz     short loc_180027667
0x180027677  mov     rax, r8
0x18002767a  mov     edx, 80070057h
0x18002767f  neg     rax
0x180027682  mov     rcx, r9
0x180027685  mov     rax, r8
0x180027688  sbb     ebx, ebx
0x18002768a  sub     rcx, r8
0x18002768d  not     ebx
0x18002768f  and     ebx, edx
0x180027691  neg     rax
0x180027694  sbb     rsi, rsi
0x180027697  and     rsi, rcx
0x18002769a  test    r8, r8
0x18002769d  jz      loc_180027739
0x1800276a3  mov     rdi, [rsp+48h+String2]
0x1800276a8  test    rdi, rdi
0x1800276ab  jz      short loc_180027724
0x1800276ad  mov     rcx, r9
0x1800276b0  mov     rax, rdi
0x1800276b3  cmp     [rax], r15w
0x1800276b7  jz      short loc_1800276C3
0x1800276b9  add     rax, 2
0x1800276bd  sub     rcx, 1
0x1800276c1  jnz     short loc_1800276B3
0x1800276c3  mov     rax, rcx
0x1800276c6  neg     rax
0x1800276c9  mov     rax, rcx
0x1800276cc  sbb     ebx, ebx
0x1800276ce  sub     r9, rcx
0x1800276d1  not     ebx
0x1800276d3  and     ebx, edx
0x1800276d5  neg     rax
0x1800276d8  sbb     rdx, rdx
0x1800276db  and     rdx, r9
0x1800276de  test    rcx, rcx
0x1800276e1  jnz     short loc_1800276E7
0x1800276e3  mov     edx, ebx
0x1800276e5  jmp     short loc_180027726
0x1800276e7  cmp     rdx, rsi
0x1800276ea  ja      short loc_1800276F1
0x1800276ec  mov     [r14], r15d
0x1800276ef  jmp     short loc_180027758
0x1800276f1  mov     r8, rsi; MaxCount
0x1800276f4  mov     rdx, rdi; String2
0x1800276f7  mov     rcx, rbp; String1
0x1800276fa  call    cs:__imp__wcsnicmp
0x180027700  test    eax, eax
0x180027702  jnz     short loc_1800276EC
0x180027704  cmp     word ptr [rbp+rsi*2-2], 5Ch ; '\'
0x18002770a  jz      short loc_18002771B
0x18002770c  cmp     word ptr [rdi+rsi*2], 5Ch ; '\'
0x180027711  jnz     short loc_1800276EC
0x180027713  cmp     [rdi+rsi*2+2], r15w
0x180027719  jz      short loc_1800276EC
0x18002771b  mov     dword ptr [r14], 1
0x180027722  jmp     short loc_180027758
0x180027724  mov     ebx, edx
0x180027726  mov     r9d, edx
0x180027729  mov     r8d, 7B2h
0x18002772f  jmp     loc_180027618
0x180027734  mov     ebx, 80070057h
0x180027739  mov     r9d, ebx; int
0x18002773c  mov     r8d, 7AFh; int
0x180027742  lea     rdx, aSdpissubdirect; "SdpIsSubDirectory"
0x180027749  mov     ecx, 1; Level
0x18002774e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027753  mov     rdi, [rsp+48h+String2]
0x180027758  test    rbp, rbp
0x18002775b  jz      short loc_180027765
0x18002775d  mov     rcx, rbp; Block
0x180027760  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027765  test    rdi, rdi
0x180027768  jz      short loc_180027772
0x18002776a  mov     rcx, rdi; Block
0x18002776d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027772  mov     eax, ebx
0x180027774  mov     rbx, [rsp+48h+arg_8]
0x180027779  add     rsp, 20h
0x18002777d  pop     r15
0x18002777f  pop     r14
0x180027781  pop     rdi
0x180027782  pop     rsi
0x180027783  pop     rbp
0x180027784  retn
```
