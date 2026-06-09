# TSetEventMasksOrSubMasks

- ea: `0x180035050`
- end: `0x180035276`
- name: `TSetEventMasksOrSubMasks`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x18001c7c0`
- `0x180034604`
- `0x180034694`
- `0x180034768`
- `0x18003483c`
- `0x18003490c`
- `0x1800349dc`
- `0x180035050`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180035089`
- `KERNEL32!GetCurrentThreadId` at `0x18003522f`
- `KERNEL32!GetCurrentThreadId` at `0x180035089`
- `KERNEL32!GetCurrentThreadId` at `0x18003522f`
- `KERNEL32!LeaveCriticalSection` at `0x180035255`
- `KERNEL32!LeaveCriticalSection` at `0x180035255`
- `KERNEL32!EnterCriticalSection` at `0x180035079`
- `KERNEL32!EnterCriticalSection` at `0x180035079`

## pseudocode

```c
_DWORD *__fastcall TSetEventMasksOrSubMasks(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // rdi
  size_t v8; // rdx
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // edx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  size_t v22; // rdx
  _DWORD *result; // rax

  v7 = *(_QWORD *)(a2 + 24);
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 758;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v8, "\\server\\event.c");
  if ( (~qword_1800519A0 & v7) == 0 )
  {
    v9 = *(_DWORD *)(a2 + 8);
    if ( !v9 )
    {
      *(_DWORD *)a2 = SettClientEventMasks(a1, *(unsigned int *)(a2 + 16), v7, *(unsigned int *)(a2 + 20));
      goto LABEL_27;
    }
    v10 = (unsigned int)(v9 - 1);
    if ( (_DWORD)v10 )
    {
      v11 = (unsigned int)(v10 - 1);
      if ( (_DWORD)v11 )
      {
        v12 = (unsigned int)(v11 - 1);
        if ( (_DWORD)v12 )
        {
          v13 = (unsigned int)(v12 - 1);
          if ( (_DWORD)v13 )
          {
            if ( (_DWORD)v13 != 1 )
            {
              *(_DWORD *)a2 = -2147483576;
LABEL_27:
              dword_1800519F8 = 930;
              goto LABEL_28;
            }
            v14 = ReferenceObject(v13, *(unsigned int *)(a2 + 12), 1229734736);
            if ( !v14 )
            {
              *(_DWORD *)a2 = -1879048173;
              goto LABEL_27;
            }
            v15 = SettPhoneClientEventMasks(v14, *(unsigned int *)(a2 + 16), v7, *(unsigned int *)(a2 + 20));
          }
          else
          {
            v18 = ReferenceObject(v13, *(unsigned int *)(a2 + 12), 1347436880);
            if ( !v18 )
            {
              *(_DWORD *)a2 = -1879048185;
              goto LABEL_27;
            }
            v15 = SettPhoneAppEventMasks(v18, *(unsigned int *)(a2 + 16), v7, *(unsigned int *)(a2 + 20));
          }
        }
        else
        {
          v19 = ReferenceObject(v12, *(unsigned int *)(a2 + 12), 1229734723);
          if ( !v19 )
          {
            *(_DWORD *)a2 = -2147483624;
            goto LABEL_27;
          }
          v15 = SettCallClientEventMasks(v19, *(unsigned int *)(a2 + 16), v7, *(unsigned int *)(a2 + 20));
        }
      }
      else
      {
        v20 = ReferenceObject(v11, *(unsigned int *)(a2 + 12), 1229734732);
        if ( !v20 )
        {
          *(_DWORD *)a2 = -2147483605;
          goto LABEL_27;
        }
        v15 = SettLineClientEventMasks(v20, *(unsigned int *)(a2 + 16), v7, *(unsigned int *)(a2 + 20));
      }
    }
    else
    {
      v21 = ReferenceObject(v10, *(unsigned int *)(a2 + 12), 1347436876);
      if ( !v21 )
      {
        *(_DWORD *)a2 = -2147483628;
        goto LABEL_27;
      }
      v15 = SettLineAppEventMasks(v21, *(unsigned int *)(a2 + 16), v7, *(unsigned int *)(a2 + 20));
    }
    v17 = *(_DWORD *)(a2 + 12);
    *(_DWORD *)a2 = v15;
    DereferenceObject(v16, v17, 1);
    goto LABEL_27;
  }
  *(_DWORD *)a2 = -2147483598;
  dword_1800519F8 = 762;
LABEL_28:
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v22, "\\server\\event.c");
  LeaveCriticalSection(&CriticalSection);
  result = a5;
  *a5 = 32;
  return result;
}

```

## disassembly

```asm
0x180035050  mov     [rsp+arg_0], rbx
0x180035055  mov     [rsp+arg_8], rsi
0x18003505a  push    rdi
0x18003505b  sub     rsp, 20h
0x18003505f  mov     edi, [rdx+1Ch]
0x180035062  mov     rsi, rcx
0x180035065  mov     eax, [rdx+18h]
0x180035068  lea     rcx, CriticalSection; lpCriticalSection
0x18003506f  shl     rdi, 20h
0x180035073  mov     rbx, rdx
0x180035076  or      rdi, rax
0x180035079  call    cs:__imp_EnterCriticalSection
0x18003507f  mov     cs:dword_1800519E0, 2F6h
0x180035089  call    cs:__imp_GetCurrentThreadId
0x18003508f  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x180035096  mov     cs:dword_1800519E4, eax
0x18003509c  lea     rcx, pszDest; pszDest
0x1800350a3  call    StringCbCopyA
0x1800350a8  mov     r10, cs:qword_1800519A0
0x1800350af  not     r10
0x1800350b2  test    rdi, r10
0x1800350b5  jz      short loc_1800350CC
0x1800350b7  mov     dword ptr [rbx], 80000032h
0x1800350bd  mov     cs:dword_1800519F8, 2FAh
0x1800350c7  jmp     loc_18003522F
0x1800350cc  mov     ecx, [rbx+8]
0x1800350cf  test    ecx, ecx
0x1800350d1  jz      loc_180035211
0x1800350d7  sub     ecx, 1
0x1800350da  jz      loc_1800351DF
0x1800350e0  sub     ecx, 1
0x1800350e3  jz      loc_1800351AD
0x1800350e9  sub     ecx, 1
0x1800350ec  jz      loc_18003517E
0x1800350f2  sub     ecx, 1
0x1800350f5  jz      short loc_18003514C
0x1800350f7  cmp     ecx, 1
0x1800350fa  jz      short loc_180035107
0x1800350fc  mov     dword ptr [rbx], 80000048h
0x180035102  jmp     loc_180035225
0x180035107  mov     edx, [rbx+0Ch]
0x18003510a  mov     r8d, 494C4350h
0x180035110  call    ReferenceObject
0x180035115  test    rax, rax
0x180035118  jz      short loc_180035141
0x18003511a  mov     r9d, [rbx+14h]
0x18003511e  mov     r8, rdi
0x180035121  mov     edx, [rbx+10h]
0x180035124  mov     rcx, rax
0x180035127  call    SettPhoneClientEventMasks
0x18003512c  mov     edx, [rbx+0Ch]
0x18003512f  mov     r8d, 1
0x180035135  mov     [rbx], eax
0x180035137  call    DereferenceObject
0x18003513c  jmp     loc_180035225
0x180035141  mov     dword ptr [rbx], 90000013h
0x180035147  jmp     loc_180035225
0x18003514c  mov     edx, [rbx+0Ch]
0x18003514f  mov     r8d, 50504150h
0x180035155  call    ReferenceObject
0x18003515a  test    rax, rax
0x18003515d  jz      short loc_180035173
0x18003515f  mov     r9d, [rbx+14h]
0x180035163  mov     r8, rdi
0x180035166  mov     edx, [rbx+10h]
0x180035169  mov     rcx, rax
0x18003516c  call    SettPhoneAppEventMasks
0x180035171  jmp     short loc_18003512C
0x180035173  mov     dword ptr [rbx], 90000007h
0x180035179  jmp     loc_180035225
0x18003517e  mov     edx, [rbx+0Ch]
0x180035181  mov     r8d, 494C4343h
0x180035187  call    ReferenceObject
0x18003518c  test    rax, rax
0x18003518f  jz      short loc_1800351A5
0x180035191  mov     r9d, [rbx+14h]
0x180035195  mov     r8, rdi
0x180035198  mov     edx, [rbx+10h]
0x18003519b  mov     rcx, rax
0x18003519e  call    SettCallClientEventMasks
0x1800351a3  jmp     short loc_18003512C
0x1800351a5  mov     dword ptr [rbx], 80000018h
0x1800351ab  jmp     short loc_180035225
0x1800351ad  mov     edx, [rbx+0Ch]
0x1800351b0  mov     r8d, 494C434Ch
0x1800351b6  call    ReferenceObject
0x1800351bb  test    rax, rax
0x1800351be  jz      short loc_1800351D7
0x1800351c0  mov     r9d, [rbx+14h]
0x1800351c4  mov     r8, rdi
0x1800351c7  mov     edx, [rbx+10h]
0x1800351ca  mov     rcx, rax
0x1800351cd  call    SettLineClientEventMasks
0x1800351d2  jmp     loc_18003512C
0x1800351d7  mov     dword ptr [rbx], 8000002Bh
0x1800351dd  jmp     short loc_180035225
0x1800351df  mov     edx, [rbx+0Ch]
0x1800351e2  mov     r8d, 5050414Ch
0x1800351e8  call    ReferenceObject
0x1800351ed  test    rax, rax
0x1800351f0  jz      short loc_180035209
0x1800351f2  mov     r9d, [rbx+14h]
0x1800351f6  mov     r8, rdi
0x1800351f9  mov     edx, [rbx+10h]
0x1800351fc  mov     rcx, rax
0x1800351ff  call    SettLineAppEventMasks
0x180035204  jmp     loc_18003512C
0x180035209  mov     dword ptr [rbx], 80000014h
0x18003520f  jmp     short loc_180035225
0x180035211  mov     r9d, [rbx+14h]
0x180035215  mov     r8, rdi
0x180035218  mov     edx, [rbx+10h]
0x18003521b  mov     rcx, rsi
0x18003521e  call    SettClientEventMasks
0x180035223  mov     [rbx], eax
0x180035225  mov     cs:dword_1800519F8, 3A2h
0x18003522f  call    cs:__imp_GetCurrentThreadId
0x180035235  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x18003523c  mov     cs:dword_1800519FC, eax
0x180035242  lea     rcx, byte_1800519E8; pszDest
0x180035249  call    StringCbCopyA
0x18003524e  lea     rcx, CriticalSection; lpCriticalSection
0x180035255  call    cs:__imp_LeaveCriticalSection
0x18003525b  mov     rax, [rsp+28h+arg_20]
0x180035260  mov     rbx, [rsp+28h+arg_0]
0x180035265  mov     rsi, [rsp+28h+arg_8]
0x18003526a  mov     dword ptr [rax], 20h ; ' '
0x180035270  add     rsp, 20h
0x180035274  pop     rdi
0x180035275  retn
```
