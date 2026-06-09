# SOS_OS::GetThreadControlRegisters(ulong,void * *,void * *)

- ea: `0x1004b9100`
- end: `0x1004b9361`
- name: `?GetThreadControlRegisters@SOS_OS@@SA?AW4SOS_RESULT@@KPEAPEAX0@Z`
- size: `609`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100403070`
- `0x100411fb0`
- `0x1004b9100`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1004b9153`
- `KERNEL32!GetCurrentThreadId` at `0x1004b9153`
- `KERNEL32!OpenThread` at `0x1004b9178`
- `KERNEL32!OpenThread` at `0x1004b9178`
- `KERNEL32!GetThreadContext` at `0x1004b9235`
- `KERNEL32!GetThreadContext` at `0x1004b9235`
- `KERNEL32!CloseHandle` at `0x1004b931b`
- `KERNEL32!CloseHandle` at `0x1004b931b`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x1004b92e1`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x1004b92e1`

## pseudocode

```c
__int64 __fastcall SOS_OS::GetThreadControlRegisters(DWORD a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  void *v7; // rsi
  _QWORD *v8; // rax
  HANDLE v9; // r14
  CONTEXT *p_Context; // rcx
  _OWORD *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rdx
  _OWORD *v14; // rax
  CONTEXT *v15; // rcx
  _QWORD v17[5]; // [rsp+28h] [rbp-1870h] BYREF
  _BYTE v18[48]; // [rsp+50h] [rbp-1848h] BYREF
  int v19; // [rsp+80h] [rbp-1818h]
  __int64 v20; // [rsp+E8h] [rbp-17B0h]
  void *v21; // [rsp+148h] [rbp-1750h]
  CONTEXT Context; // [rsp+520h] [rbp-1378h] BYREF

  v17[3] = a2;
  v17[4] = a3;
  v6 = 0x80000000;
  v17[0] = 0;
  v7 = 0;
  v17[1] = 0;
  if ( GetCurrentThreadId() == a1 )
  {
    v8 = v17;
    v7 = &SOS_OS::GetThreadControlRegisters;
    v6 = 0;
  }
  else
  {
    v9 = OpenThread(0x48u, 0, a1);
    v17[2] = v9;
    if ( v9 )
    {
      v19 = 1048577;
      p_Context = &Context;
      v11 = v18;
      v12 = 9;
      v13 = 9;
      do
      {
        *(_OWORD *)&p_Context->P1Home = *v11;
        *(_OWORD *)&p_Context->P3Home = v11[1];
        *(_OWORD *)&p_Context->P5Home = v11[2];
        *(_OWORD *)&p_Context->ContextFlags = v11[3];
        *(_OWORD *)&p_Context->SegGs = v11[4];
        *(_OWORD *)&p_Context->Dr1 = v11[5];
        *(_OWORD *)&p_Context->Dr3 = v11[6];
        p_Context = (CONTEXT *)((char *)p_Context + 128);
        *(_OWORD *)&p_Context[-1].LastExceptionToRip = v11[7];
        v11 += 8;
        --v13;
      }
      while ( v13 );
      *(_OWORD *)&p_Context->P1Home = *v11;
      *(_OWORD *)&p_Context->P3Home = v11[1];
      *(_OWORD *)&p_Context->P5Home = v11[2];
      *(_OWORD *)&p_Context->ContextFlags = v11[3];
      *(_OWORD *)&p_Context->SegGs = v11[4];
      if ( GetThreadContext(v9, &Context) )
      {
        v6 = 0;
        v14 = v18;
        v15 = &Context;
        do
        {
          *v14 = *(_OWORD *)&v15->P1Home;
          v14[1] = *(_OWORD *)&v15->P3Home;
          v14[2] = *(_OWORD *)&v15->P5Home;
          v14[3] = *(_OWORD *)&v15->ContextFlags;
          v14[4] = *(_OWORD *)&v15->SegGs;
          v14[5] = *(_OWORD *)&v15->Dr1;
          v14[6] = *(_OWORD *)&v15->Dr3;
          v14 += 8;
          *(v14 - 1) = *(_OWORD *)&v15->Dr7;
          v15 = (CONTEXT *)((char *)v15 + 128);
          --v12;
        }
        while ( v12 );
        *v14 = *(_OWORD *)&v15->P1Home;
        v14[1] = *(_OWORD *)&v15->P3Home;
        v14[2] = *(_OWORD *)&v15->P5Home;
        v14[3] = *(_OWORD *)&v15->ContextFlags;
        v14[4] = *(_OWORD *)&v15->SegGs;
      }
      if ( !v6 )
      {
        v17[0] = v20;
        v7 = v21;
      }
      CloseHandle(v9);
    }
    v8 = (_QWORD *)v17[0];
  }
  if ( a2 )
    *a2 = v8;
  if ( a3 )
    *a3 = v7;
  return v6;
}

```

## disassembly

```asm
0x1004b9100  mov     [rsp+arg_18], rbx
0x1004b9105  push    rsi
0x1004b9106  push    rdi
0x1004b9107  push    r12
0x1004b9109  push    r14
0x1004b910b  push    r15
0x1004b910d  mov     eax, 1870h
0x1004b9112  call    _alloca_probe
0x1004b9117  sub     rsp, rax
0x1004b911a  mov     rax, cs:__security_cookie
0x1004b9121  xor     rax, rsp
0x1004b9124  mov     [rsp+1898h+var_38], rax
0x1004b912c  mov     r15, r8
0x1004b912f  mov     r12, rdx
0x1004b9132  mov     edi, ecx
0x1004b9134  mov     [rsp+1898h+var_1858], rdx
0x1004b9139  mov     [rsp+1898h+var_1850], r8
0x1004b913e  mov     ebx, 80000000h
0x1004b9143  mov     [rsp+1898h+var_1870], 0
0x1004b914c  xor     esi, esi
0x1004b914e  mov     [rsp+1898h+var_1868], rsi
0x1004b9153  call    cs:__imp_GetCurrentThreadId
0x1004b9159  cmp     eax, edi
0x1004b915b  jnz     short loc_1004B9170
0x1004b915d  lea     rax, [rsp+1898h+var_1870]
0x1004b9162  lea     rsi, ?GetThreadControlRegisters@SOS_OS@@SA?AW4SOS_RESULT@@KPEAPEAX0@Z; SOS_OS::GetThreadControlRegisters(ulong,void * *,void * *)
0x1004b9169  xor     ebx, ebx
0x1004b916b  jmp     loc_1004B9326
0x1004b9170  mov     r8d, edi; dwThreadId
0x1004b9173  xor     edx, edx; bInheritHandle
0x1004b9175  lea     ecx, [rdx+48h]; dwDesiredAccess
0x1004b9178  call    cs:__imp_OpenThread
0x1004b917e  mov     r14, rax
0x1004b9181  mov     [rsp+1898h+var_1860], rax
0x1004b9186  test    rax, rax
0x1004b9189  jz      loc_1004B9321
0x1004b918f  mov     [rsp+1898h+var_1818], 100001h
0x1004b919a  mov     [rsp+1898h+var_1878], ebx
0x1004b919e  lea     rcx, [rsp+1898h+Context]
0x1004b91a6  lea     rax, [rsp+1898h+var_1848]
0x1004b91ab  mov     edi, 9
0x1004b91b0  mov     edx, edi
0x1004b91b2  movups  xmm0, xmmword ptr [rax]
0x1004b91b5  movups  xmmword ptr [rcx], xmm0
0x1004b91b8  movups  xmm1, xmmword ptr [rax+10h]
0x1004b91bc  movups  xmmword ptr [rcx+10h], xmm1
0x1004b91c0  movups  xmm0, xmmword ptr [rax+20h]
0x1004b91c4  movups  xmmword ptr [rcx+20h], xmm0
0x1004b91c8  movups  xmm1, xmmword ptr [rax+30h]
0x1004b91cc  movups  xmmword ptr [rcx+30h], xmm1
0x1004b91d0  movups  xmm0, xmmword ptr [rax+40h]
0x1004b91d4  movups  xmmword ptr [rcx+40h], xmm0
0x1004b91d8  movups  xmm1, xmmword ptr [rax+50h]
0x1004b91dc  movups  xmmword ptr [rcx+50h], xmm1
0x1004b91e0  movups  xmm0, xmmword ptr [rax+60h]
0x1004b91e4  movups  xmmword ptr [rcx+60h], xmm0
0x1004b91e8  lea     rcx, [rcx+80h]
0x1004b91ef  movups  xmm1, xmmword ptr [rax+70h]
0x1004b91f3  movups  xmmword ptr [rcx-10h], xmm1
0x1004b91f7  lea     rax, [rax+80h]
0x1004b91fe  sub     rdx, 1
0x1004b9202  jnz     short loc_1004B91B2
0x1004b9204  movups  xmm0, xmmword ptr [rax]
0x1004b9207  movups  xmmword ptr [rcx], xmm0
0x1004b920a  movups  xmm1, xmmword ptr [rax+10h]
0x1004b920e  movups  xmmword ptr [rcx+10h], xmm1
0x1004b9212  movups  xmm0, xmmword ptr [rax+20h]
0x1004b9216  movups  xmmword ptr [rcx+20h], xmm0
0x1004b921a  movups  xmm1, xmmword ptr [rax+30h]
0x1004b921e  movups  xmmword ptr [rcx+30h], xmm1
0x1004b9222  movups  xmm0, xmmword ptr [rax+40h]
0x1004b9226  movups  xmmword ptr [rcx+40h], xmm0
0x1004b922a  lea     rdx, [rsp+1898h+Context]; lpContext
0x1004b9232  mov     rcx, r14; hThread
0x1004b9235  call    cs:__imp_GetThreadContext
0x1004b923b  test    eax, eax
0x1004b923d  jz      loc_1004B92D8
0x1004b9243  xor     ebx, ebx
0x1004b9245  mov     [rsp+1898h+var_1878], ebx
0x1004b9249  lea     rax, [rsp+1898h+var_1848]
0x1004b924e  lea     rcx, [rsp+1898h+Context]
0x1004b9256  nop     word ptr [rax+rax+00000000h]
0x1004b9260  movups  xmm0, xmmword ptr [rcx]
0x1004b9263  movups  xmmword ptr [rax], xmm0
0x1004b9266  movups  xmm1, xmmword ptr [rcx+10h]
0x1004b926a  movups  xmmword ptr [rax+10h], xmm1
0x1004b926e  movups  xmm0, xmmword ptr [rcx+20h]
0x1004b9272  movups  xmmword ptr [rax+20h], xmm0
0x1004b9276  movups  xmm1, xmmword ptr [rcx+30h]
0x1004b927a  movups  xmmword ptr [rax+30h], xmm1
0x1004b927e  movups  xmm0, xmmword ptr [rcx+40h]
0x1004b9282  movups  xmmword ptr [rax+40h], xmm0
0x1004b9286  movups  xmm1, xmmword ptr [rcx+50h]
0x1004b928a  movups  xmmword ptr [rax+50h], xmm1
0x1004b928e  movups  xmm0, xmmword ptr [rcx+60h]
0x1004b9292  movups  xmmword ptr [rax+60h], xmm0
0x1004b9296  lea     rax, [rax+80h]
0x1004b929d  movups  xmm1, xmmword ptr [rcx+70h]
0x1004b92a1  movups  xmmword ptr [rax-10h], xmm1
0x1004b92a5  lea     rcx, [rcx+80h]
0x1004b92ac  sub     rdi, 1
0x1004b92b0  jnz     short loc_1004B9260
0x1004b92b2  movups  xmm0, xmmword ptr [rcx]
0x1004b92b5  movups  xmmword ptr [rax], xmm0
0x1004b92b8  movups  xmm1, xmmword ptr [rcx+10h]
0x1004b92bc  movups  xmmword ptr [rax+10h], xmm1
0x1004b92c0  movups  xmm0, xmmword ptr [rcx+20h]
0x1004b92c4  movups  xmmword ptr [rax+20h], xmm0
0x1004b92c8  movups  xmm1, xmmword ptr [rcx+30h]
0x1004b92cc  movups  xmmword ptr [rax+30h], xmm1
0x1004b92d0  movups  xmm0, xmmword ptr [rcx+40h]
0x1004b92d4  movups  xmmword ptr [rax+40h], xmm0
0x1004b92d8  jmp     short loc_1004B92FF
0x1004b92da  cmp     eax, 0C00000FDh
0x1004b92df  jnz     short loc_1004B92E7
0x1004b92e1  call    cs:__imp__resetstkoflw
0x1004b92e7  mov     ebx, [rsp+1898h+var_1878]
0x1004b92eb  mov     rsi, [rsp+1898h+var_1868]
0x1004b92f0  mov     r14, [rsp+1898h+var_1860]
0x1004b92f5  mov     r12, [rsp+1898h+var_1858]
0x1004b92fa  mov     r15, [rsp+1898h+var_1850]
0x1004b92ff  test    ebx, ebx
0x1004b9301  jnz     short loc_1004B9318
0x1004b9303  mov     rax, [rsp+1898h+var_17B0]
0x1004b930b  mov     [rsp+1898h+var_1870], rax
0x1004b9310  mov     rsi, [rsp+1898h+var_1750]
0x1004b9318  mov     rcx, r14; hObject
0x1004b931b  call    cs:__imp_CloseHandle
0x1004b9321  mov     rax, [rsp+1898h+var_1870]
0x1004b9326  test    r12, r12
0x1004b9329  jz      short loc_1004B932F
0x1004b932b  mov     [r12], rax
0x1004b932f  test    r15, r15
0x1004b9332  jz      short loc_1004B9337
0x1004b9334  mov     [r15], rsi
0x1004b9337  mov     eax, ebx
0x1004b9339  mov     rcx, [rsp+1898h+var_38]
0x1004b9341  xor     rcx, rsp; StackCookie
0x1004b9344  call    __security_check_cookie
0x1004b9349  mov     rbx, [rsp+1898h+arg_18]
0x1004b9351  add     rsp, 1870h
0x1004b9358  pop     r15
0x1004b935a  pop     r14
0x1004b935c  pop     r12
0x1004b935e  pop     rdi
0x1004b935f  pop     rsi
0x1004b9360  retn
```
