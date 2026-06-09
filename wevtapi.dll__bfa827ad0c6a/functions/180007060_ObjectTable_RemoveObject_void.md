# ObjectTable::RemoveObject(void *)

- ea: `0x180007060`
- end: `0x180007170`
- name: `?RemoveObject@ObjectTable@@QEAAKPEAX@Z`
- size: `272`
- prototype: `unsigned int __fastcall(ObjectTable *__hidden this, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006df4`
- `0x180006e40`
- `0x180007010`

## callees

- `0x180006870`
- `0x180007060`
- `0x18000a100`
- `0x180023548`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800070cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800070cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800070ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800070ee`

## pseudocode

```c
__int64 __fastcall ObjectTable::RemoveObject(ObjectTable *this, void *a2)
{
  __int64 v2; // rax
  RTL_SRWLOCK *v3; // rbx
  unsigned int v4; // edx
  int v5; // esi
  _QWORD *Ptr; // rbp
  __int64 v7; // rdi
  wmi::RefBase *v8; // r14

  v2 = (unsigned int)a2 >> 24;
  if ( (unsigned int)v2 < 0x18
    && (v3 = &g_objectTable + 2 * v2 + v2 + 1, SLODWORD(v3[2].Ptr) > 0)
    && v3
    && (v4 = (unsigned int)a2 & 0xFFFFFF, v5 = v4 - 1, (int)(v4 - 1) >= 0)
    && v5 < SLODWORD(v3->Ptr)
    && (Ptr = v3[1].Ptr, v7 = 2LL * v4, LOBYTE(Ptr[2 * v4 - 2])) )
  {
    v8 = (wmi::RefBase *)Ptr[2 * v4 - 1];
    AcquireSRWLockExclusive(&g_objectTable);
    if ( (int)--LODWORD(v3[2].Ptr) <= 0 )
    {
      operator delete(v3[1].Ptr);
      v5 = -1;
      v3[1].Ptr = 0;
      LODWORD(v3->Ptr) = 0;
    }
    else
    {
      LOBYTE(Ptr[v7 - 2]) = 0;
      LODWORD(Ptr[v7 - 1]) = HIDWORD(v3[2].Ptr);
    }
    HIDWORD(v3[2].Ptr) = v5;
    ReleaseSRWLockExclusive(&g_objectTable);
    *((_QWORD *)v8 + 2) = 0;
    wmi::RefBase::Release(v8);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bdd8dfecdda73f662b5cb6975e6dc96d_Traceguids, 6);
    }
    return 6;
  }
}

```

## disassembly

```asm
0x180007060  push    rbx
0x180007062  push    rbp
0x180007063  push    rsi
0x180007064  push    rdi
0x180007065  push    r12
0x180007067  push    r14
0x180007069  sub     rsp, 28h
0x18000706d  mov     eax, edx
0x18000706f  shr     eax, 18h
0x180007072  cmp     eax, 18h
0x180007075  jnb     loc_18000712F
0x18000707b  lea     rbx, ds:1[rax*2]
0x180007083  add     rbx, rax
0x180007086  lea     r12, ?g_objectTable@@3VObjectTable@@A; ObjectTable g_objectTable
0x18000708d  lea     rbx, [r12+rbx*8]
0x180007091  cmp     dword ptr [rbx+10h], 0
0x180007095  jle     loc_18000712F
0x18000709b  test    rbx, rbx
0x18000709e  jz      loc_18000712F
0x1800070a4  and     edx, 0FFFFFFh
0x1800070aa  lea     esi, [rdx-1]
0x1800070ad  test    esi, esi
0x1800070af  js      short loc_18000712F
0x1800070b1  cmp     esi, [rbx]
0x1800070b3  jge     short loc_18000712F
0x1800070b5  mov     rbp, [rbx+8]
0x1800070b9  mov     edi, edx
0x1800070bb  add     rdi, rdi
0x1800070be  cmp     byte ptr [rbp+rdi*8-10h], 0
0x1800070c3  jz      short loc_18000712F
0x1800070c5  mov     r14, [rbp+rdi*8-8]
0x1800070ca  mov     rcx, r12; SRWLock
0x1800070cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800070d3  dec     dword ptr [rbx+10h]
0x1800070d6  cmp     dword ptr [rbx+10h], 0
0x1800070da  jle     short loc_180007113
0x1800070dc  mov     byte ptr [rbp+rdi*8-10h], 0
0x1800070e1  mov     eax, [rbx+14h]
0x1800070e4  mov     [rbp+rdi*8-8], eax
0x1800070e8  mov     rcx, r12; SRWLock
0x1800070eb  mov     [rbx+14h], esi
0x1800070ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800070f4  mov     rcx, r14; this
0x1800070f7  mov     qword ptr [r14+10h], 0
0x1800070ff  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180007104  xor     eax, eax
0x180007106  add     rsp, 28h
0x18000710a  pop     r14
0x18000710c  pop     r12
0x18000710e  pop     rdi
0x18000710f  pop     rsi
0x180007110  pop     rbp
0x180007111  pop     rbx
0x180007112  retn
0x180007113  mov     rcx, [rbx+8]; void *
0x180007117  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000711c  or      esi, 0FFFFFFFFh
0x18000711f  mov     qword ptr [rbx+8], 0
0x180007127  mov     dword ptr [rbx], 0
0x18000712d  jmp     short loc_1800070E8
0x18000712f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007136  lea     rax, WPP_GLOBAL_Control
0x18000713d  mov     ebx, 6
0x180007142  cmp     rcx, rax
0x180007145  jz      short loc_18000716C
0x180007147  test    dword ptr [rcx+1Ch], 40000h
0x18000714e  jz      short loc_18000716C
0x180007150  cmp     byte ptr [rcx+19h], 2
0x180007154  jb      short loc_18000716C
0x180007156  mov     rcx, [rcx+10h]
0x18000715a  lea     edx, [rbx+4]
0x18000715d  mov     r9d, ebx
0x180007160  lea     r8, WPP_bdd8dfecdda73f662b5cb6975e6dc96d_Traceguids
0x180007167  call    WPP_SF_D
0x18000716c  mov     eax, ebx
0x18000716e  jmp     short loc_180007106
```
