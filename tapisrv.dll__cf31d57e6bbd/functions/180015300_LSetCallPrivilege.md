# LSetCallPrivilege

- ea: `0x180015300`
- end: `0x1800154ec`
- name: `LSetCallPrivilege`
- size: `492`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180028100`

## callees

- `0x180015300`
- `0x18001bb04`
- `0x18001f620`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180015403`
- `KERNEL32!LeaveCriticalSection` at `0x180015470`
- `KERNEL32!LeaveCriticalSection` at `0x180015403`
- `KERNEL32!LeaveCriticalSection` at `0x180015470`

## string_xrefs

- `0x1800154c7`: `LineEpilogSync: (lineSetCallPrivilege) exit, result=x%x`

## pseudocode

```c
__int64 __fastcall LSetCallPrivilege(__int64 a1, _DWORD *a2)
{
  unsigned int *v4; // r14
  __int64 v5; // rax
  __int64 v6; // rcx
  _DWORD *v7; // rsi
  unsigned __int64 v8; // rdi
  int v9; // eax
  int v10; // ecx
  int v11; // r9d

  v4 = a2 + 2;
  v5 = ReferenceObject(a1, (unsigned int)a2[2], 1229734723);
  v7 = (_DWORD *)v5;
  if ( v5 )
  {
    v8 = *(_QWORD *)(v5 + 24);
    if ( *(_DWORD *)v5 == 1229734723 && *(_QWORD *)(v5 + 8) == a1 )
    {
      if ( ((a2[3] - 2) & 0xFFFFFFFD) != 0 )
      {
        *a2 = -2147483622;
      }
      else if ( (unsigned int)WaitForExclusivetCallAccess(v8, 1280065859) )
      {
        if ( *v7 == 1229734723 )
        {
          v9 = a2[3];
          if ( v9 != v7[8] )
          {
            v10 = *(_DWORD *)(v8 + 64);
            if ( v9 == 4 )
            {
              *(_DWORD *)(v8 + 64) = v10 + 1;
              --*(_DWORD *)(v8 + 68);
            }
            else
            {
              *(_DWORD *)(v8 + 64) = v10 - 1;
              ++*(_DWORD *)(v8 + 68);
            }
            v7[8] = a2[3];
            LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits
                                                                 & (v8 >> 4)));
            v11 = 10240;
            if ( a2[3] != 4 )
              v11 = 12288;
            SendMsgToCallClients(v8, (_DWORD)v7, 1, v11, 0, 0);
            goto LABEL_20;
          }
        }
        else
        {
          *a2 = -2147483624;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v8 >> 4)));
      }
      else
      {
        *a2 = -2147483624;
      }
    }
    else
    {
      v6 = dword_180051918 != 0 ? -2147483624 : -2147483568;
      *a2 = v6;
    }
LABEL_20:
    DereferenceObject(v6, *v4, 1);
    return TRACELogPrint(524290, "LineEpilogSync: (lineSetCallPrivilege) exit, result=x%x", *a2);
  }
  *a2 = dword_180051918 != 0 ? -2147483624 : -2147483568;
  return TRACELogPrint(524290, "LineEpilogSync: (lineSetCallPrivilege) exit, result=x%x", *a2);
}

```

## disassembly

```asm
0x180015300  mov     [rsp+arg_0], rbx
0x180015305  mov     [rsp+arg_10], rsi
0x18001530a  mov     [rsp+arg_8], rdx
0x18001530f  push    rdi
0x180015310  push    r14
0x180015312  push    r15
0x180015314  sub     rsp, 40h
0x180015318  mov     rbx, rdx
0x18001531b  mov     r15, rcx
0x18001531e  lea     r14, [rdx+8]
0x180015322  mov     [rsp+58h+var_28], r14
0x180015327  mov     r8d, 494C4343h
0x18001532d  mov     edx, [r14]
0x180015330  call    ReferenceObject
0x180015335  mov     rsi, rax
0x180015338  test    rax, rax
0x18001533b  jnz     short loc_180015357
0x18001533d  mov     eax, cs:dword_180051918
0x180015343  neg     eax
0x180015345  sbb     ecx, ecx
0x180015347  and     ecx, 0FFFFFFC8h
0x18001534a  add     ecx, 80000050h
0x180015350  mov     [rbx], ecx
0x180015352  jmp     loc_1800154C4
0x180015357  mov     rdi, [rax+18h]
0x18001535b  mov     [rsp+58h+var_20], rdi
0x180015360  cmp     dword ptr [rax], 494C4343h
0x180015366  jnz     loc_180015480
0x18001536c  cmp     [rax+8], r15
0x180015370  jnz     loc_180015480
0x180015376  mov     eax, [rbx+0Ch]
0x180015379  sub     eax, 2
0x18001537c  test    eax, 0FFFFFFFDh
0x180015381  jz      short loc_18001538E
0x180015383  mov     dword ptr [rbx], 8000001Ah
0x180015389  jmp     loc_1800154B6
0x18001538e  mov     edx, 4C4C4143h
0x180015393  mov     rcx, rdi
0x180015396  call    WaitForExclusivetCallAccess
0x18001539b  test    eax, eax
0x18001539d  jz      loc_180015478
0x1800153a3  cmp     dword ptr [rsi], 494C4343h
0x1800153a9  jz      short loc_1800153B6
0x1800153ab  mov     dword ptr [rbx], 80000018h
0x1800153b1  jmp     loc_180015454
0x1800153b6  mov     eax, [rbx+0Ch]
0x1800153b9  cmp     eax, [rsi+20h]
0x1800153bc  jz      loc_180015454
0x1800153c2  mov     ecx, [rdi+40h]
0x1800153c5  cmp     eax, 4
0x1800153c8  jnz     short loc_1800153D5
0x1800153ca  lea     eax, [rcx+1]
0x1800153cd  mov     [rdi+40h], eax
0x1800153d0  dec     dword ptr [rdi+44h]
0x1800153d3  jmp     short loc_1800153DE
0x1800153d5  lea     eax, [rcx-1]
0x1800153d8  mov     [rdi+40h], eax
0x1800153db  inc     dword ptr [rdi+44h]
0x1800153de  mov     eax, [rbx+0Ch]
0x1800153e1  mov     [rsi+20h], eax
0x1800153e4  mov     rdx, rdi
0x1800153e7  shr     rdx, 4
0x1800153eb  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800153f1  and     rdx, rax
0x1800153f4  lea     rdx, [rdx+rdx*4]
0x1800153f8  mov     rax, cs:gLockTable
0x1800153ff  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180015403  call    cs:__imp_LeaveCriticalSection
0x180015409  mov     eax, 3000h
0x18001540e  mov     r9d, 2800h
0x180015414  cmp     dword ptr [rbx+0Ch], 4
0x180015418  cmovnz  r9d, eax
0x18001541c  mov     [rsp+58h+var_30], 0
0x180015424  mov     [rsp+58h+var_38], 0
0x18001542c  mov     r8d, 1
0x180015432  mov     rdx, rsi
0x180015435  mov     rcx, rdi
0x180015438  call    SendMsgToCallClients
0x18001543d  jmp     short loc_1800154B6
0x18001543f  mov     rbx, [rsp+58h+arg_8]
0x180015444  mov     dword ptr [rbx], 80000018h
0x18001544a  mov     rdi, [rsp+58h+var_20]
0x18001544f  mov     r14, [rsp+58h+var_28]
0x180015454  shr     rdi, 4
0x180015458  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001545e  and     rdi, rax
0x180015461  lea     rcx, [rdi+rdi*4]
0x180015465  mov     rax, cs:gLockTable
0x18001546c  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180015470  call    cs:__imp_LeaveCriticalSection
0x180015476  jmp     short loc_1800154B6
0x180015478  mov     dword ptr [rbx], 80000018h
0x18001547e  jmp     short loc_1800154B6
0x180015480  mov     eax, cs:dword_180051918
0x180015486  neg     eax
0x180015488  sbb     ecx, ecx
0x18001548a  and     ecx, 0FFFFFFC8h
0x18001548d  add     ecx, 80000050h
0x180015493  mov     [rbx], ecx
0x180015495  jmp     short loc_1800154B6
0x180015497  mov     eax, cs:dword_180051918
0x18001549d  neg     eax
0x18001549f  sbb     ecx, ecx
0x1800154a1  and     ecx, 0FFFFFFC8h
0x1800154a4  add     ecx, 80000050h
0x1800154aa  mov     rbx, [rsp+58h+arg_8]
0x1800154af  mov     [rbx], ecx
0x1800154b1  mov     r14, [rsp+58h+var_28]
0x1800154b6  mov     r8d, 1
0x1800154bc  mov     edx, [r14]
0x1800154bf  call    DereferenceObject
0x1800154c4  mov     r8d, [rbx]
0x1800154c7  lea     rdx, aLineepilogsync_0; "LineEpilogSync: (lineSetCallPrivilege) "...
0x1800154ce  mov     ecx, 80002h
0x1800154d3  call    TRACELogPrint
0x1800154d8  mov     rbx, [rsp+58h+arg_0]
0x1800154dd  mov     rsi, [rsp+58h+arg_10]
0x1800154e2  add     rsp, 40h
0x1800154e6  pop     r15
0x1800154e8  pop     r14
0x1800154ea  pop     rdi
0x1800154eb  retn
```
