# CTpSrvDataState::UpdateCacheSize(int)

- ea: `0x180012530`
- end: `0x18001269f`
- name: `?UpdateCacheSize@CTpSrvDataState@@AEAAXH@Z`
- size: `367`
- prototype: `void __fastcall(CTpSrvDataState *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180012a60`
- `0x180013c10`

## callees

- `0x180012530`
- `0x1800247d4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180012698`
- `KERNEL32!EnterCriticalSection` at `0x180012555`
- `KERNEL32!EnterCriticalSection` at `0x180012555`

## pseudocode

```c
void __fastcall CTpSrvDataState::UpdateCacheSize(CTpSrvDataState *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  LONGLONG v5; // rax
  LONGLONG v6; // rsi
  LONGLONG v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // eax
  unsigned __int64 v12; // rcx
  unsigned int v13; // ecx
  unsigned int v14; // edx
  float v15; // xmm0_4
  int v16; // eax
  unsigned int v17; // r8d

  v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  EnterCriticalSection(v2);
  v5 = CStopwatch::CurrentMs((CTpSrvDataState *)((char *)this + 648));
  v6 = v5;
  if ( a2 )
  {
    v7 = CStopwatch::CurrentMs((CTpSrvDataState *)((char *)this + 648));
    v8 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 72) = v7;
    if ( v6 - *((_QWORD *)this + 71) > (unsigned __int64)*(unsigned int *)(v8 + 48) )
    {
      v9 = *((_DWORD *)this + 139);
      v10 = 2;
      *((_QWORD *)this + 71) = v6;
      v11 = (int)(float)((float)v9 * 0.80000001);
      if ( v11 > 2 )
        v10 = v11;
LABEL_20:
      *((_DWORD *)this + 139) = v10;
    }
  }
  else
  {
    v12 = *(unsigned int *)(*((_QWORD *)this + 3) + 44LL);
    if ( v5 - *((_QWORD *)this + 72) > v12 && v5 - *((_QWORD *)this + 70) > v12 && v5 - *((_QWORD *)this + 71) > v12 )
    {
      v13 = *((_DWORD *)this + 139);
      v14 = *((_DWORD *)this + 138);
      if ( v13 < v14 && !*((_DWORD *)this + 136) )
      {
        if ( v13 >= v14 >> 1 )
          v15 = FLOAT_0_25;
        else
          v15 = FLOAT_0_75;
        v16 = (int)(float)((float)(int)v13 * v15);
        if ( !v16 )
          v16 = 1;
        v17 = v13 + v16;
        v10 = 2;
        if ( v17 >= 2 )
        {
          v10 = *((_DWORD *)this + 138);
          if ( v17 <= v14 )
            v10 = v17;
        }
        *((_QWORD *)this + 70) = v6;
        goto LABEL_20;
      }
    }
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180012530  mov     rax, rsp
0x180012533  mov     [rax+8], rbx
0x180012537  mov     [rax+10h], rbp
0x18001253b  mov     [rax+18h], rsi
0x18001253f  mov     [rax+20h], rdi
0x180012543  push    r14
0x180012545  sub     rsp, 20h
0x180012549  mov     r14, [rcx+8]
0x18001254d  mov     rdi, rcx
0x180012550  mov     rcx, r14; lpCriticalSection
0x180012553  mov     ebx, edx
0x180012555  call    cs:__imp_EnterCriticalSection
0x18001255b  lea     rbp, [rdi+288h]
0x180012562  mov     rcx, rbp; this
0x180012565  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001256a  mov     rsi, rax
0x18001256d  test    ebx, ebx
0x18001256f  jz      short loc_1800125CB
0x180012571  mov     rcx, rbp; this
0x180012574  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x180012579  mov     rcx, [rdi+18h]
0x18001257d  mov     [rdi+240h], rax
0x180012584  mov     edx, [rcx+30h]
0x180012587  mov     rcx, rsi
0x18001258a  sub     rcx, [rdi+238h]
0x180012591  cmp     rcx, rdx
0x180012594  jbe     loc_18001267B
0x18001259a  mov     eax, [rdi+22Ch]
0x1800125a0  xorps   xmm0, xmm0
0x1800125a3  mov     ecx, 2
0x1800125a8  mov     [rdi+238h], rsi
0x1800125af  cvtsi2ss xmm0, rax
0x1800125b4  mulss   xmm0, cs:__real@3f4ccccd
0x1800125bc  cvttss2si rax, xmm0
0x1800125c1  cmp     eax, ecx
0x1800125c3  cmova   ecx, eax
0x1800125c6  jmp     loc_180012675
0x1800125cb  mov     rax, [rdi+18h]
0x1800125cf  mov     ecx, [rax+2Ch]
0x1800125d2  mov     rax, rsi
0x1800125d5  sub     rax, [rdi+240h]
0x1800125dc  cmp     rax, rcx
0x1800125df  jbe     loc_18001267B
0x1800125e5  mov     rax, rsi
0x1800125e8  sub     rax, [rdi+230h]
0x1800125ef  cmp     rax, rcx
0x1800125f2  jbe     loc_18001267B
0x1800125f8  mov     rax, rsi
0x1800125fb  sub     rax, [rdi+238h]
0x180012602  cmp     rax, rcx
0x180012605  jbe     short loc_18001267B
0x180012607  mov     ecx, [rdi+22Ch]
0x18001260d  mov     edx, [rdi+228h]
0x180012613  cmp     ecx, edx
0x180012615  jnb     short loc_18001267B
0x180012617  cmp     dword ptr [rdi+220h], 0
0x18001261e  jnz     short loc_18001267B
0x180012620  mov     eax, edx
0x180012622  xorps   xmm1, xmm1
0x180012625  shr     eax, 1
0x180012627  cvtsi2ss xmm1, rcx
0x18001262c  cmp     ecx, eax
0x18001262e  jnb     short loc_18001263A
0x180012630  movss   xmm0, cs:__real@3f400000
0x180012638  jmp     short loc_180012642
0x18001263a  movss   xmm0, cs:__real@3e800000
0x180012642  mov     r8d, 1
0x180012648  mulss   xmm1, xmm0
0x18001264c  cvttss2si rax, xmm1
0x180012651  test    eax, eax
0x180012653  cmovz   eax, r8d
0x180012657  lea     r8d, [rcx+rax]
0x18001265b  mov     ecx, 2
0x180012660  cmp     r8d, ecx
0x180012663  jb      short loc_18001266E
0x180012665  cmp     r8d, edx
0x180012668  mov     ecx, edx
0x18001266a  cmovbe  ecx, r8d
0x18001266e  mov     [rdi+230h], rsi
0x180012675  mov     [rdi+22Ch], ecx
0x18001267b  mov     rcx, r14
0x18001267e  mov     rbx, [rsp+28h+arg_0]
0x180012683  mov     rbp, [rsp+28h+arg_8]
0x180012688  mov     rsi, [rsp+28h+arg_10]
0x18001268d  mov     rdi, [rsp+28h+arg_18]
0x180012692  add     rsp, 20h
0x180012696  pop     r14
0x180012698  jmp     cs:__imp_LeaveCriticalSection
```
