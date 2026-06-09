# CreateDpiCursors(HICON__ *,HINSTANCE__ *,ushort const *,ulong,ulong,ulong)

- ea: `0x180008324`
- end: `0x1800084e2`
- name: `?CreateDpiCursors@@YAXPEAUHICON__@@PEAUHINSTANCE__@@PEBGKKK@Z`
- size: `446`
- prototype: `void __usercall(HICON@<rcx>, HINSTANCE@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180002f70`
- `0x1800038b0`
- `0x180005950`
- `0x180006dd8`
- `0x18005c4f0`

## callees

- `0x180003034`
- `0x180005f7c`
- `0x1800070e0`
- `0x180007640`
- `0x1800081d4`
- `0x180008324`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserLinkDpiCursor` at `0x180008462`
- `win32u!NtUserLinkDpiCursor` at `0x180008462`
- `win32u!NtUserGetRequiredCursorSizes` at `0x1800083c6`
- `win32u!NtUserGetRequiredCursorSizes` at `0x1800083c6`
- `win32u!NtUserGetIconSize` at `0x180008398`
- `win32u!NtUserGetIconSize` at `0x180008398`
- `win32u!NtUserDestroyCursor` at `0x180008476`
- `win32u!NtUserDestroyCursor` at `0x180008476`

## pseudocode

```c
void __fastcall CreateDpiCursors(
        HICON a1,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        int DpiDependentMetric,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edi
  unsigned int ThreadDefCursorSize; // r15d
  __int64 i; // rbx
  int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // r8d
  HICON v20; // rax
  HICON v21; // rsi
  unsigned int DpiForSystem; // eax
  unsigned int v23; // eax
  unsigned int v24; // [rsp+30h] [rbp-48h] BYREF
  int v25; // [rsp+34h] [rbp-44h] BYREF
  _OWORD v26[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v27; // [rsp+58h] [rbp-20h]

  if ( a1 )
  {
    v25 = 0;
    v24 = 0;
    if ( !gbDisableDpiCursorScaling && LODWORD(NtCurrentTeb()->Win32ClientInfo[34]) != 1 && (a6 & 0x40000) == 0 )
    {
      if ( (unsigned int)NtUserGetIconSize(a1, 0, &v25, &v24) )
      {
        v12 = v24 >> 1;
      }
      else
      {
        if ( !DpiDependentMetric )
        {
          DpiForSystem = GetDpiForSystem(v11, v10);
          DpiDependentMetric = GetDpiDependentMetric(7, DpiForSystem);
        }
        v12 = a5;
        v25 = DpiDependentMetric;
        if ( !a5 )
        {
          v23 = GetDpiForSystem(v11, v10);
          v12 = GetDpiDependentMetric(7, v23);
        }
      }
      v24 = v12;
      v27 = 0;
      memset(v26, 0, sizeof(v26));
      if ( (unsigned int)NtUserGetRequiredCursorSizes(a1, v26) )
      {
        v13 = a6 & 0xFFFBFFBF | 0x40000;
        ThreadDefCursorSize = GetThreadDefCursorSize();
        for ( i = 0; i != 5; ++i )
        {
          if ( *((_DWORD *)v26 + 2 * i) )
          {
            v16 = *((_DWORD *)v26 + 2 * i + 1);
            if ( v16 != ThreadDefCursorSize )
            {
              v17 = v25 * v16;
              v18 = v24 * v16;
              v19 = v17 / ThreadDefCursorSize;
              if ( a2 || a3 )
                v20 = (HICON)ObjectFromDIBResource(a2, a3, (unsigned __int16 *)1, v19, v18 / ThreadDefCursorSize, v13);
              else
                v20 = CopyIcoCur(a1, 0, v19, v18 / ThreadDefCursorSize, v13, 1);
              v21 = v20;
              if ( !(unsigned int)NtUserLinkDpiCursor(a1, v20, *((unsigned int *)v26 + 2 * i + 1)) )
                NtUserDestroyCursor(v21, 1);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180008324  test    rcx, rcx
0x180008327  jnz     short loc_18000832A
0x180008329  retn
0x18000832a  push    rbp
0x18000832b  push    rbx
0x18000832c  push    rsi
0x18000832d  push    rdi
0x18000832e  push    r12
0x180008330  push    r13
0x180008332  push    r14
0x180008334  push    r15
0x180008336  mov     rbp, rsp
0x180008339  sub     rsp, 78h
0x18000833d  mov     rax, cs:__security_cookie
0x180008344  xor     rax, rsp
0x180008347  mov     [rbp+var_18], rax
0x18000834b  cmp     cs:?gbDisableDpiCursorScaling@@3HA, 0; int gbDisableDpiCursorScaling
0x180008352  mov     ebx, r9d
0x180008355  mov     edi, [rbp+arg_28]
0x180008358  mov     r12, r8
0x18000835b  mov     r13, rdx
0x18000835e  mov     [rbp+var_44], 0
0x180008365  mov     r14, rcx
0x180008368  mov     [rbp+var_48], 0
0x18000836f  jnz     short loc_1800083F0
0x180008371  mov     rax, gs:30h
0x18000837a  cmp     dword ptr [rax+910h], 1
0x180008381  jz      short loc_1800083F0
0x180008383  mov     r15d, 40000h
0x180008389  test    r15d, edi
0x18000838c  jnz     short loc_1800083F0
0x18000838e  lea     r9, [rbp+var_48]
0x180008392  xor     edx, edx
0x180008394  lea     r8, [rbp+var_44]
0x180008398  call    cs:__imp_NtUserGetIconSize
0x18000839e  test    eax, eax
0x1800083a0  jz      loc_180008481
0x1800083a6  mov     eax, [rbp+var_48]
0x1800083a9  shr     eax, 1
0x1800083ab  xorps   xmm0, xmm0
0x1800083ae  mov     [rbp+var_48], eax
0x1800083b1  xor     eax, eax
0x1800083b3  lea     rdx, [rbp+var_40]
0x1800083b7  mov     rcx, r14
0x1800083ba  mov     [rbp+var_20], rax
0x1800083be  movups  [rbp+var_40], xmm0
0x1800083c2  movups  [rbp+var_30], xmm0
0x1800083c6  call    cs:__imp_NtUserGetRequiredCursorSizes
0x1800083cc  test    eax, eax
0x1800083ce  jz      short loc_1800083F0
0x1800083d0  and     edi, 0FFFFFFBFh
0x1800083d3  or      edi, r15d
0x1800083d6  call    ?GetThreadDefCursorSize@@YAHXZ; GetThreadDefCursorSize(void)
0x1800083db  mov     r15d, eax
0x1800083de  xor     ebx, ebx
0x1800083e0  cmp     dword ptr [rbp+rbx*8+var_40], 0
0x1800083e5  jnz     short loc_18000840D
0x1800083e7  inc     rbx
0x1800083ea  cmp     rbx, 5
0x1800083ee  jnz     short loc_1800083E0
0x1800083f0  mov     rcx, [rbp+var_18]
0x1800083f4  xor     rcx, rsp; StackCookie
0x1800083f7  call    __security_check_cookie
0x1800083fc  add     rsp, 78h
0x180008400  pop     r15
0x180008402  pop     r14
0x180008404  pop     r13
0x180008406  pop     r12
0x180008408  pop     rdi
0x180008409  pop     rsi
0x18000840a  pop     rbx
0x18000840b  pop     rbp
0x18000840c  retn
0x18000840d  mov     ecx, dword ptr [rbp+rbx*8+var_40+4]
0x180008411  cmp     ecx, r15d
0x180008414  jz      short loc_1800083E7
0x180008416  xor     edx, edx
0x180008418  mov     eax, ecx
0x18000841a  imul    eax, [rbp+var_44]
0x18000841e  imul    ecx, [rbp+var_48]
0x180008422  div     r15d
0x180008425  xor     edx, edx
0x180008427  mov     r8d, eax; int
0x18000842a  mov     eax, ecx
0x18000842c  div     r15d
0x18000842f  test    r13, r13
0x180008432  jz      loc_1800084BB
0x180008438  mov     r9d, r8d; nWidth
0x18000843b  mov     [rsp+78h+var_50], edi; unsigned int
0x18000843f  mov     r8d, 1; unsigned __int16 *
0x180008445  mov     [rsp+78h+var_58], eax; unsigned int
0x180008449  mov     rdx, r12; unsigned __int16 *
0x18000844c  mov     rcx, r13; HINSTANCE
0x18000844f  call    ?ObjectFromDIBResource@@YAPEAXPEAUHINSTANCE__@@PEBGPEAGKKI@Z; ObjectFromDIBResource(HINSTANCE__ *,ushort const *,ushort *,ulong,ulong,uint)
0x180008454  mov     r8d, dword ptr [rbp+rbx*8+var_40+4]
0x180008459  mov     rdx, rax
0x18000845c  mov     rcx, r14
0x18000845f  mov     rsi, rax
0x180008462  call    cs:__imp_NtUserLinkDpiCursor
0x180008468  test    eax, eax
0x18000846a  jnz     loc_1800083E7
0x180008470  lea     edx, [rax+1]
0x180008473  mov     rcx, rsi
0x180008476  call    cs:__imp_NtUserDestroyCursor
0x18000847c  jmp     loc_1800083E7
0x180008481  mov     esi, 7
0x180008486  test    ebx, ebx
0x180008488  jnz     short loc_18000849A
0x18000848a  call    GetDpiForSystem
0x18000848f  mov     edx, eax
0x180008491  mov     ecx, esi
0x180008493  call    GetDpiDependentMetric
0x180008498  mov     ebx, eax
0x18000849a  mov     eax, [rbp+arg_20]
0x18000849d  mov     [rbp+var_44], ebx
0x1800084a0  test    eax, eax
0x1800084a2  jnz     loc_1800083AB
0x1800084a8  call    GetDpiForSystem
0x1800084ad  mov     edx, eax
0x1800084af  mov     ecx, esi
0x1800084b1  call    GetDpiDependentMetric
0x1800084b6  jmp     loc_1800083AB
0x1800084bb  test    r12, r12
0x1800084be  jnz     loc_180008438
0x1800084c4  mov     [rsp+78h+var_50], 1; int
0x1800084cc  mov     r9d, eax; int
0x1800084cf  xor     edx, edx; int
0x1800084d1  mov     [rsp+78h+var_58], edi; unsigned int
0x1800084d5  mov     rcx, r14; HICON
0x1800084d8  call    ?CopyIcoCur@@YAPEAUHICON__@@PEAU1@HHHIH@Z; CopyIcoCur(HICON__ *,int,int,int,uint,int)
0x1800084dd  jmp     loc_180008454
```
