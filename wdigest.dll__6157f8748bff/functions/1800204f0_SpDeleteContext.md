# SpDeleteContext

- ea: `0x1800204f0`
- end: `0x1800206c5`
- name: `SpDeleteContext`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18000fa94`
- `0x180011b28`
- `0x1800185b8`
- `0x180018b18`
- `0x1800192a8`
- `0x18001a394`
- `0x1800204f0`
- `0x180038010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180020650`
- `ntdll!RtlEnterCriticalSection` at `0x180020650`

## pseudocode

```c
__int64 __fastcall SpDeleteContext(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  HLOCAL v7; // rdi
  int v8; // eax
  __int128 v10; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+40h] [rbp-48h]
  HLOCAL hMem; // [rsp+98h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, a1);
  hMem = 0;
  LOBYTE(a2) = 1;
  v11 = 0;
  v10 = 0;
  v3 = CtxtHandlerHandleToContext(a1, a2, &hMem);
  if ( (v3 & 0x80000000) != 0 )
  {
    v3 = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v5 = 11;
      v6 = 0;
      goto LABEL_24;
    }
    goto LABEL_26;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(*(_QWORD *)&g_LsaFunctions + 192LL))(&v10) )
    goto LABEL_18;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, HIDWORD(v10));
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 4) != 0 )
      {
        WPP_SF_d(v4[2], 13, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, DWORD2(v10));
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      {
        WPP_SF_dd(v4[2], 14, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, (unsigned int)v10, DWORD1(v10));
LABEL_18:
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  v7 = hMem;
  if ( hMem )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)hMem + 648));
    v8 = CtxtHandlerRelease(v7);
    v3 = v8;
    if ( v8 >= 0 )
    {
LABEL_25:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    v5 = 15;
    v6 = (unsigned int)v8;
LABEL_24:
    WPP_SF_d(v4[2], v5, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v6);
    goto LABEL_25;
  }
LABEL_26:
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 )
    WPP_SF_qD(v4[2], 17, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, a1, v3);
  return v3;
}

```

## disassembly

```asm
0x1800204f0  push    rbx
0x1800204f2  push    rbp
0x1800204f3  push    rsi
0x1800204f4  push    rdi
0x1800204f5  push    r14
0x1800204f7  push    r15
0x1800204f9  sub     rsp, 58h
0x1800204fd  mov     rsi, rcx
0x180020500  mov     rcx, cs:WPP_GLOBAL_Control
0x180020507  lea     r14, WPP_GLOBAL_Control
0x18002050e  lea     r15, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x180020515  cmp     rcx, r14
0x180020518  jz      short loc_180020534
0x18002051a  test    byte ptr [rcx+1Ch], 80h
0x18002051e  jz      short loc_180020534
0x180020520  mov     rcx, [rcx+10h]
0x180020524  mov     edx, 0Ah
0x180020529  mov     r9, rsi
0x18002052c  mov     r8, r15
0x18002052f  call    WPP_SF_q
0x180020534  xorps   xmm0, xmm0
0x180020537  mov     [rsp+88h+hMem], 0
0x180020543  xor     eax, eax
0x180020545  lea     r8, [rsp+88h+hMem]
0x18002054d  mov     dl, 1
0x18002054f  mov     [rsp+88h+var_48], rax
0x180020554  mov     rcx, rsi
0x180020557  movups  [rsp+88h+var_58], xmm0
0x18002055c  call    CtxtHandlerHandleToContext
0x180020561  mov     ebx, eax
0x180020563  test    eax, eax
0x180020565  jns     short loc_18002058E
0x180020567  xor     ebx, ebx
0x180020569  mov     rcx, cs:WPP_GLOBAL_Control
0x180020570  cmp     rcx, r14
0x180020573  jz      loc_1800206B6
0x180020579  test    byte ptr [rcx+1Ch], 4
0x18002057d  jz      loc_180020693
0x180020583  lea     edx, [rbx+0Bh]
0x180020586  xor     r9d, r9d
0x180020589  jmp     loc_180020680
0x18002058e  mov     rax, cs:g_LsaFunctions
0x180020595  lea     rcx, [rsp+88h+var_58]
0x18002059a  mov     ebp, 1
0x18002059f  mov     rax, [rax+0C0h]
0x1800205a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205ab  test    al, al
0x1800205ad  jz      loc_180020635
0x1800205b3  mov     ebp, dword ptr [rsp+88h+var_58+0Ch]
0x1800205b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205be  cmp     rcx, r14
0x1800205c1  jz      short loc_18002063C
0x1800205c3  test    byte ptr [rcx+1Ch], 4
0x1800205c7  jz      short loc_1800205E4
0x1800205c9  mov     rcx, [rcx+10h]
0x1800205cd  mov     edx, 0Ch
0x1800205d2  mov     r9d, ebp
0x1800205d5  mov     r8, r15
0x1800205d8  call    WPP_SF_d
0x1800205dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205e4  cmp     rcx, r14
0x1800205e7  jz      short loc_18002063C
0x1800205e9  test    byte ptr [rcx+1Ch], 4
0x1800205ed  jz      short loc_18002060C
0x1800205ef  mov     r9d, dword ptr [rsp+88h+var_58+8]
0x1800205f4  mov     edx, 0Dh
0x1800205f9  mov     rcx, [rcx+10h]
0x1800205fd  mov     r8, r15
0x180020600  call    WPP_SF_d
0x180020605  mov     rcx, cs:WPP_GLOBAL_Control
0x18002060c  cmp     rcx, r14
0x18002060f  jz      short loc_18002063C
0x180020611  test    byte ptr [rcx+1Ch], 4
0x180020615  jz      short loc_18002063C
0x180020617  mov     eax, dword ptr [rsp+88h+var_58+4]
0x18002061b  mov     edx, 0Eh
0x180020620  mov     r9d, dword ptr [rsp+88h+var_58]
0x180020625  mov     r8, r15
0x180020628  mov     rcx, [rcx+10h]
0x18002062c  mov     [rsp+88h+var_68], eax
0x180020630  call    WPP_SF_dd
0x180020635  mov     rcx, cs:WPP_GLOBAL_Control
0x18002063c  mov     rdi, [rsp+88h+hMem]
0x180020644  test    rdi, rdi
0x180020647  jz      short loc_180020693
0x180020649  lea     rcx, [rdi+288h]; CriticalSection
0x180020650  call    cs:__imp_RtlEnterCriticalSection
0x180020656  mov     edx, ebp
0x180020658  mov     rcx, rdi; hMem
0x18002065b  call    CtxtHandlerRelease
0x180020660  mov     ebx, eax
0x180020662  test    eax, eax
0x180020664  jns     short loc_18002068C
0x180020666  mov     rcx, cs:WPP_GLOBAL_Control
0x18002066d  cmp     rcx, r14
0x180020670  jz      short loc_1800206B6
0x180020672  test    byte ptr [rcx+1Ch], 1
0x180020676  jz      short loc_180020693
0x180020678  mov     edx, 0Fh
0x18002067d  mov     r9d, eax
0x180020680  mov     rcx, [rcx+10h]
0x180020684  mov     r8, r15
0x180020687  call    WPP_SF_d
0x18002068c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020693  cmp     rcx, r14
0x180020696  jz      short loc_1800206B6
0x180020698  test    byte ptr [rcx+1Ch], 80h
0x18002069c  jz      short loc_1800206B6
0x18002069e  mov     rcx, [rcx+10h]
0x1800206a2  mov     edx, 11h
0x1800206a7  mov     r9, rsi
0x1800206aa  mov     [rsp+88h+var_68], ebx
0x1800206ae  mov     r8, r15
0x1800206b1  call    WPP_SF_qD
0x1800206b6  mov     eax, ebx
0x1800206b8  add     rsp, 58h
0x1800206bc  pop     r15
0x1800206be  pop     r14
0x1800206c0  pop     rdi
0x1800206c1  pop     rsi
0x1800206c2  pop     rbp
0x1800206c3  pop     rbx
0x1800206c4  retn
```
