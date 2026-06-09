# LCreateAgentSession

- ea: `0x180009010`
- end: `0x1800092dd`
- name: `LCreateAgentSession`
- size: `717`
- prototype: `__int64 __fastcall(int, _DWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180028100`

## callees

- `0x1800038cc`
- `0x1800063d4`
- `0x180006f24`
- `0x180007244`
- `0x1800072e4`
- `0x180009010`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c114`
- `0x18001c854`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180009226`
- `KERNEL32!HeapAlloc` at `0x180009226`
- `KERNEL32!lstrlenW` at `0x180009171`
- `KERNEL32!lstrlenW` at `0x180009171`

## pseudocode

```c
__int64 __fastcall LCreateAgentSession(int a1, _DWORD *a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r8d
  __int64 result; // rax
  int v10; // eax
  __int64 v11; // rsi
  int v12; // edi
  unsigned int v13; // edx
  int Proxy; // eax
  bool v15; // zf
  unsigned int v16; // r14d
  __int64 v17; // r11
  __int64 v18; // rcx
  int v19; // eax
  LPVOID v20; // rax
  __int64 v21; // r9
  __int64 v22; // [rsp+70h] [rbp-1h] BYREF
  __int64 v23; // [rsp+78h] [rbp+7h] BYREF
  __int64 v24; // [rsp+80h] [rbp+Fh] BYREF
  int v25[2]; // [rsp+88h] [rbp+17h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+1Fh] BYREF
  __int64 v27; // [rsp+D8h] [rbp+67h] BYREF

  v5 = a2[6];
  TargetHandle = 0;
  *(_QWORD *)v25 = 0;
  v22 = 0;
  v24 = 0;
  v27 = 0;
  if ( v5 == -1 || (result = IsBadStringParam(a3, a4, v5), !(_DWORD)result) )
  {
    result = IsBadSizeOffset(a3, 0, a2[9], a2[8], 4);
    if ( !(_DWORD)result && a2[9] >= 0x10u )
    {
      v10 = LineProlog(
              a1,
              2,
              a2[4],
              (int)v25,
              0,
              &TargetHandle,
              (__int64)&v22 + 4,
              0,
              0,
              (__int64)&v27,
              a2[2],
              (__int64)&v22,
              (__int64)&v24);
      v11 = v27;
      v12 = v10;
      if ( v10 <= 0 )
        return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v22), v11, v22);
      v13 = a2[7];
      LODWORD(v27) = 0;
      v23 = 0;
      Proxy = FindProxy(v24, v13, 0xCu, &v23, &v27, 0x20002u);
      if ( Proxy )
      {
LABEL_7:
        v12 = Proxy;
        return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v22), v11, v22);
      }
      *(_QWORD *)(v11 + 80) = (unsigned int)a2[10];
      *(_QWORD *)(v11 + 88) = 4;
      *(_DWORD *)(v11 + 68) = a2[3];
      if ( v23 )
      {
        v15 = a2[6] == -1;
        v16 = 0;
        v27 = 0;
        if ( !v15 )
          v16 = 2 * lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[6])) + 2;
        Proxy = CreateProxyRequest(v23, 0xCu, v16 + 36, v11, (ULONG **)&v27);
        if ( Proxy )
          goto LABEL_7;
        v17 = v27;
        if ( v16 )
        {
          *(_DWORD *)(v27 + 72) = v16;
          *(_DWORD *)(v17 + 76) = 36;
          StringCbCopyW((STRSAFE_LPWSTR)(v17 + 104), v16, (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[6]));
        }
        v18 = v23;
        *(_OWORD *)(v17 + 84) = *(_OWORD *)((unsigned int)a2[8] + a4);
        *(_DWORD *)(v17 + 100) = a2[7];
        *(_DWORD *)(v17 + 80) = a2[5];
        Proxy = SendProxyRequest(v18, v17, v11);
        if ( Proxy )
          goto LABEL_7;
        v19 = *(_DWORD *)(v11 + 72);
      }
      else
      {
        if ( !*((_DWORD *)GetLineLookupEntry(v27) + 9) )
        {
          v12 = -2147483575;
          return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v22), v11, v22);
        }
        v20 = HeapAlloc(ghTapisrvHeap, 8u, 0x2Cu);
        if ( !v20 )
        {
          v12 = -2147483580;
          return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v22), v11, v22);
        }
        *(_QWORD *)(v11 + 48) = LCreateAgent_PostProcess;
        *(_QWORD *)(v11 + 96) = v20;
        if ( a2[6] == -1 )
          v21 = 0;
        else
          v21 = a4 + (unsigned int)a2[6];
        v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, __int64, __int64))(pRemoteSP + 1080))(
                *(unsigned int *)(v11 + 72),
                *(_QWORD *)v25,
                (unsigned int)a2[5],
                v21,
                a2[7],
                a4 + (unsigned int)a2[8],
                (__int64)v20 + 40);
      }
      *a2 = v19;
      return LineEpilogAsync((_DWORD)a2, v12, (_DWORD)TargetHandle, HIDWORD(v22), v11, v22);
    }
  }
  *a2 = -2147483576;
  return result;
}

```

## disassembly

```asm
0x180009010  mov     [rsp-8+arg_0], rbx
0x180009015  mov     [rsp-8+arg_10], rsi
0x18000901a  push    rbp
0x18000901b  push    rdi
0x18000901c  push    r13
0x18000901e  push    r14
0x180009020  push    r15
0x180009022  lea     rbp, [rsp-2Fh]
0x180009027  sub     rsp, 0A0h
0x18000902e  xor     r13d, r13d
0x180009031  mov     edi, r8d
0x180009034  mov     r8d, [rdx+18h]
0x180009038  or      r14d, 0FFFFFFFFh
0x18000903c  mov     dword ptr [rbp+4Fh+var_50+4], r13d
0x180009040  mov     r15, r9
0x180009043  mov     [rbp+4Fh+TargetHandle], r13
0x180009047  mov     rbx, rdx
0x18000904a  mov     qword ptr [rbp+4Fh+var_38], r13
0x18000904e  mov     rsi, rcx
0x180009051  mov     dword ptr [rbp+4Fh+var_50], r13d
0x180009055  mov     [rbp+4Fh+var_40], r13
0x180009059  mov     [rbp+4Fh+arg_8], r13
0x18000905d  cmp     r8d, r14d
0x180009060  jz      short loc_180009074
0x180009062  mov     rdx, r9
0x180009065  mov     ecx, edi
0x180009067  call    IsBadStringParam
0x18000906c  test    eax, eax
0x18000906e  jnz     loc_1800092BB
0x180009074  mov     r9d, [rbx+20h]
0x180009078  xor     edx, edx
0x18000907a  mov     r8d, [rbx+24h]
0x18000907e  mov     ecx, edi
0x180009080  mov     [rsp+0C0h+var_A0], 4
0x180009088  call    IsBadSizeOffset
0x18000908d  test    eax, eax
0x18000908f  jnz     loc_1800092BB
0x180009095  cmp     dword ptr [rbx+24h], 10h
0x180009099  jb      loc_1800092BB
0x18000909f  mov     r8d, [rbx+10h]; int
0x1800090a3  lea     rax, [rbp+4Fh+var_40]
0x1800090a7  mov     [rsp+0C0h+var_60], rax; __int64
0x1800090ac  lea     r9, [rbp+4Fh+var_38]; int
0x1800090b0  lea     rax, [rbp+4Fh+var_50]
0x1800090b4  mov     edx, 2; int
0x1800090b9  mov     [rsp+0C0h+var_68], rax; __int64
0x1800090be  mov     rcx, rsi; int
0x1800090c1  mov     eax, [rbx+8]
0x1800090c4  mov     [rsp+0C0h+var_70], eax; int
0x1800090c8  lea     rax, [rbp+4Fh+arg_8]
0x1800090cc  mov     [rsp+0C0h+var_78], rax; __int64
0x1800090d1  lea     rax, [rbp+4Fh+var_50+4]
0x1800090d5  mov     [rsp+0C0h+var_80], r13; __int64
0x1800090da  mov     [rsp+0C0h+var_88], r13d; int
0x1800090df  mov     [rsp+0C0h+var_90], rax; __int64
0x1800090e4  lea     rax, [rbp+4Fh+TargetHandle]
0x1800090e8  mov     [rsp+0C0h+lpTargetHandle], rax; lpTargetHandle
0x1800090ed  mov     [rsp+0C0h+var_A0], r13d; int
0x1800090f2  call    LineProlog
0x1800090f7  mov     rsi, [rbp+4Fh+arg_8]
0x1800090fb  mov     edi, eax
0x1800090fd  test    eax, eax
0x1800090ff  jle     loc_18000929B
0x180009105  mov     edx, [rbx+1Ch]
0x180009108  lea     rax, [rbp+4Fh+arg_8]
0x18000910c  mov     rcx, [rbp+4Fh+var_40]
0x180009110  lea     r9, [rbp+4Fh+var_48]
0x180009114  mov     dword ptr [rsp+0C0h+lpTargetHandle], 20002h
0x18000911c  mov     r8d, 0Ch
0x180009122  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180009127  mov     dword ptr [rbp+4Fh+arg_8], r13d
0x18000912b  mov     [rbp+4Fh+var_48], r13
0x18000912f  call    FindProxy
0x180009134  test    eax, eax
0x180009136  jz      short loc_18000913F
0x180009138  mov     edi, eax
0x18000913a  jmp     loc_18000929B
0x18000913f  mov     eax, [rbx+28h]
0x180009142  mov     [rsi+50h], rax
0x180009146  mov     qword ptr [rsi+58h], 4
0x18000914e  mov     eax, [rbx+0Ch]
0x180009151  mov     [rsi+44h], eax
0x180009154  cmp     [rbp+4Fh+var_48], r13
0x180009158  jz      loc_180009204
0x18000915e  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x180009162  mov     r14d, r13d
0x180009165  mov     [rbp+4Fh+arg_8], r13
0x180009169  jz      short loc_18000917F
0x18000916b  mov     ecx, [rbx+18h]
0x18000916e  add     rcx, r15; lpString
0x180009171  call    cs:__imp_lstrlenW
0x180009177  lea     r14d, ds:2[rax*2]
0x18000917f  mov     rcx, [rbp+4Fh+var_48]
0x180009183  lea     rax, [rbp+4Fh+arg_8]
0x180009187  lea     r8d, [r14+24h]
0x18000918b  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180009190  mov     r9, rsi
0x180009193  mov     edx, 0Ch
0x180009198  call    CreateProxyRequest
0x18000919d  test    eax, eax
0x18000919f  jnz     short loc_180009138
0x1800091a1  mov     r11, [rbp+4Fh+arg_8]
0x1800091a5  test    r14d, r14d
0x1800091a8  jz      short loc_1800091C9
0x1800091aa  mov     [r11+48h], r14d
0x1800091ae  lea     rcx, [r11+68h]; pszDest
0x1800091b2  mov     dword ptr [r11+4Ch], 24h ; '$'
0x1800091ba  mov     r8d, [rbx+18h]
0x1800091be  add     r8, r15; pszSrc
0x1800091c1  mov     edx, r14d; cbDest
0x1800091c4  call    StringCbCopyW
0x1800091c9  mov     eax, [rbx+20h]
0x1800091cc  mov     r8, rsi
0x1800091cf  mov     rcx, [rbp+4Fh+var_48]
0x1800091d3  mov     rdx, r11
0x1800091d6  movups  xmm0, xmmword ptr [rax+r15]
0x1800091db  movdqu  xmmword ptr [r11+54h], xmm0
0x1800091e1  mov     eax, [rbx+1Ch]
0x1800091e4  mov     [r11+64h], eax
0x1800091e8  mov     eax, [rbx+14h]
0x1800091eb  mov     [r11+50h], eax
0x1800091ef  call    SendProxyRequest
0x1800091f4  test    eax, eax
0x1800091f6  jnz     loc_180009138
0x1800091fc  mov     eax, [rsi+48h]
0x1800091ff  jmp     loc_180009292
0x180009204  mov     ecx, dword ptr [rbp+4Fh+arg_8]
0x180009207  call    GetLineLookupEntry
0x18000920c  cmp     [rax+24h], r13d
0x180009210  jz      loc_180009296
0x180009216  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000921d  mov     edx, 8; dwFlags
0x180009222  lea     r8d, [rdx+24h]; dwBytes
0x180009226  call    cs:__imp_HeapAlloc
0x18000922c  test    rax, rax
0x18000922f  jnz     short loc_180009238
0x180009231  mov     edi, 80000044h
0x180009236  jmp     short loc_18000929B
0x180009238  lea     rcx, LCreateAgent_PostProcess
0x18000923f  mov     [rsi+30h], rcx
0x180009243  mov     [rsi+60h], rax
0x180009247  cmp     [rbx+18h], r14d
0x18000924b  jnz     short loc_180009252
0x18000924d  mov     r9, r13
0x180009250  jmp     short loc_180009259
0x180009252  mov     r9d, [rbx+18h]
0x180009256  add     r9, r15
0x180009259  mov     edx, [rbx+20h]
0x18000925c  lea     rcx, [rax+28h]
0x180009260  mov     rax, cs:pRemoteSP
0x180009267  add     rdx, r15
0x18000926a  mov     r8d, [rbx+14h]
0x18000926e  mov     [rsp+0C0h+var_90], rcx
0x180009273  mov     ecx, [rbx+1Ch]
0x180009276  mov     rax, [rax+438h]
0x18000927d  mov     [rsp+0C0h+lpTargetHandle], rdx
0x180009282  mov     rdx, qword ptr [rbp+4Fh+var_38]
0x180009286  mov     [rsp+0C0h+var_A0], ecx
0x18000928a  mov     ecx, [rsi+48h]
0x18000928d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009292  mov     [rbx], eax
0x180009294  jmp     short loc_18000929B
0x180009296  mov     edi, 80000049h
0x18000929b  mov     eax, dword ptr [rbp+4Fh+var_50]
0x18000929e  mov     edx, edi
0x1800092a0  mov     r9d, dword ptr [rbp+4Fh+var_50+4]
0x1800092a4  mov     rcx, rbx
0x1800092a7  mov     r8, [rbp+4Fh+TargetHandle]
0x1800092ab  mov     dword ptr [rsp+0C0h+lpTargetHandle], eax
0x1800092af  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x1800092b4  call    LineEpilogAsync
0x1800092b9  jmp     short loc_1800092C1
0x1800092bb  mov     dword ptr [rbx], 80000048h
0x1800092c1  lea     r11, [rsp+0C0h+var_20]
0x1800092c9  mov     rbx, [r11+30h]
0x1800092cd  mov     rsi, [r11+40h]
0x1800092d1  mov     rsp, r11
0x1800092d4  pop     r15
0x1800092d6  pop     r14
0x1800092d8  pop     r13
0x1800092da  pop     rdi
0x1800092db  pop     rbp
0x1800092dc  retn
```
