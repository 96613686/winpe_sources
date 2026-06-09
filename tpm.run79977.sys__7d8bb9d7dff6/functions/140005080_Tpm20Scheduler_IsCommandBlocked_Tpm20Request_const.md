# Tpm20Scheduler::IsCommandBlocked(Tpm20Request const *)

- ea: `0x140005080`
- end: `0x140005216`
- name: `?IsCommandBlocked@Tpm20Scheduler@@AEAA_NPEBVTpm20Request@@@Z`
- size: `406`
- prototype: `bool __fastcall(Tpm20Scheduler *__hidden this, const struct Tpm20Request *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000463c`

## callees

- `0x140005080`
- `0x14000dfa0`
- `0x14001be78`
- `0x1400300e0`

## pseudocode

```c
bool __fastcall Tpm20Scheduler::IsCommandBlocked(Tpm20Scheduler *this, const struct Tpm20Request *a2)
{
  char v2; // al
  bool v5; // zf
  int v6; // r8d
  int v7; // r11d
  _DWORD *v8; // r9
  unsigned int v9; // r10d
  bool v10; // al
  __int64 v11; // rdx
  int v12; // eax

  v2 = *((_BYTE *)this + 192);
  v5 = v2 == 0;
  if ( !v2 )
  {
    v6 = *(_DWORD *)((char *)a2 + 6);
    v7 = *((_DWORD *)a2 + 70);
    if ( (v6 & 0xFFFF0000) == 0x20000000 )
    {
      v10 = v7 == 2;
    }
    else
    {
      switch ( v7 )
      {
        case 2:
          v8 = &g_Allowed20Commands;
          v9 = 115;
          break;
        case 1:
          v8 = &g_Allowed20UserCommands;
          v9 = 77;
          break;
        case 3:
          v8 = &g_Allowed20AppContainerCommands;
          v9 = 33;
          break;
        default:
LABEL_9:
          if ( !*((_QWORD *)a2 + 28)
            && (v7 != 3
             || !Tpm20Scheduler::HasSystemManagementCapabilityOnIoT(this)
             || !(unsigned __int8)Tpm20Scheduler::IsCommandOnAllowList(2, *(unsigned int *)((char *)a2 + 6))) )
          {
            v12 = *((_DWORD *)a2 + 70);
            if ( v12 == 1 )
            {
              if ( *((_DWORD *)this + 45) == 123
                && (unsigned __int8)Tpm20Scheduler::IsCommandOnAllowList(2, *(unsigned int *)((char *)a2 + 6)) )
              {
                v10 = 1;
                return !v10;
              }
LABEL_13:
              v10 = 0;
              return !v10;
            }
            if ( v12 != 2 || !TpmRegistry::IsWinPE() )
              goto LABEL_13;
          }
LABEL_34:
          v10 = 1;
          return !v10;
      }
      v10 = 0;
      v11 = 0;
      do
      {
        if ( v10 )
          break;
        v10 = v8[v11] == v6;
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < v9 );
    }
    if ( v10 )
    {
      if ( v7 != 1 || v6 != 306 && (unsigned int)(v6 - 308) > 4 || *((_DWORD *)a2 + 45) < 0xEu )
        return !v10;
      if ( *(_DWORD *)(*((_QWORD *)a2 + 3) + 10LL) != 16777280 )
        goto LABEL_34;
    }
    goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x140005080  mov     [rsp+arg_8], rbx
0x140005085  push    rdi
0x140005086  sub     rsp, 20h
0x14000508a  movzx   eax, byte ptr [rcx+0C0h]
0x140005091  mov     rbx, rdx
0x140005094  mov     rdi, rcx
0x140005097  test    al, al
0x140005099  jnz     loc_14000516C
0x14000509f  mov     r8d, [rdx+6]
0x1400050a3  mov     eax, r8d
0x1400050a6  mov     r11d, [rdx+118h]
0x1400050ad  and     eax, 0FFFF0000h
0x1400050b2  cmp     eax, 20000000h
0x1400050b7  jz      loc_1400051AB
0x1400050bd  cmp     r11d, 2
0x1400050c1  jnz     short loc_140005136
0x1400050c3  lea     r9, ?g_Allowed20Commands@@3PAIA; uint near * g_Allowed20Commands
0x1400050ca  mov     r10d, 73h ; 's'
0x1400050d0  xor     al, al
0x1400050d2  mov     [rsp+28h+arg_0], rsi
0x1400050d7  xor     edx, edx
0x1400050d9  mov     esi, 1
0x1400050de  xchg    ax, ax
0x1400050e0  test    al, al
0x1400050e2  jnz     short loc_1400050F5
0x1400050e4  cmp     [r9+rdx*4], r8d
0x1400050e8  movzx   eax, al
0x1400050eb  cmovz   eax, esi
0x1400050ee  inc     edx
0x1400050f0  cmp     edx, r10d
0x1400050f3  jb      short loc_1400050E0
0x1400050f5  mov     rsi, [rsp+28h+arg_0]
0x1400050fa  test    al, al
0x1400050fc  jnz     short loc_140005164
0x1400050fe  cmp     qword ptr [rbx+0E0h], 0
0x140005106  jnz     loc_14000520F
0x14000510c  cmp     r11d, 3
0x140005110  jz      loc_1400051B7
0x140005116  mov     eax, [rbx+118h]
0x14000511c  cmp     eax, 1
0x14000511f  jnz     loc_1400051F9
0x140005125  cmp     dword ptr [rdi+0B4h], 7Bh ; '{'
0x14000512c  jz      loc_1400051DD
0x140005132  xor     al, al
0x140005134  jmp     short loc_14000516A
0x140005136  mov     ecx, r11d
0x140005139  sub     ecx, 1
0x14000513c  jnz     short loc_14000514D
0x14000513e  lea     r9, ?g_Allowed20UserCommands@@3PAIA; uint near * g_Allowed20UserCommands
0x140005145  mov     r10d, 4Dh ; 'M'
0x14000514b  jmp     short loc_1400050D0
0x14000514d  cmp     ecx, 2
0x140005150  jnz     short loc_1400050FE
0x140005152  lea     r9, ?g_Allowed20AppContainerCommands@@3PAIA; uint near * g_Allowed20AppContainerCommands
0x140005159  mov     r10d, 21h ; '!'
0x14000515f  jmp     loc_1400050D0
0x140005164  cmp     r11d, 1
0x140005168  jz      short loc_14000517B
0x14000516a  test    al, al
0x14000516c  mov     rbx, [rsp+28h+arg_8]
0x140005171  setz    al
0x140005174  add     rsp, 20h
0x140005178  pop     rdi
0x140005179  retn
0x14000517b  cmp     r8d, 132h
0x140005182  jz      short loc_140005190
0x140005184  lea     ecx, [r8-134h]
0x14000518b  cmp     ecx, 4
0x14000518e  ja      short loc_14000516A
0x140005190  cmp     dword ptr [rbx+0B4h], 0Eh
0x140005197  jb      short loc_14000516A
0x140005199  mov     rax, [rbx+18h]
0x14000519d  cmp     dword ptr [rax+0Ah], 1000040h
0x1400051a4  jnz     short loc_14000520F
0x1400051a6  jmp     loc_1400050FE
0x1400051ab  cmp     r11d, 2
0x1400051af  setz    al
0x1400051b2  jmp     loc_1400050FA
0x1400051b7  mov     rcx, rdi; this
0x1400051ba  call    ?HasSystemManagementCapabilityOnIoT@Tpm20Scheduler@@AEAA_NXZ; Tpm20Scheduler::HasSystemManagementCapabilityOnIoT(void)
0x1400051bf  test    al, al
0x1400051c1  jz      loc_140005116
0x1400051c7  mov     edx, [rbx+6]
0x1400051ca  mov     ecx, 2
0x1400051cf  call    ?IsCommandOnAllowList@Tpm20Scheduler@@CA_NW4_USER_TYPE@@I@Z; Tpm20Scheduler::IsCommandOnAllowList(_USER_TYPE,uint)
0x1400051d4  test    al, al
0x1400051d6  jnz     short loc_14000520F
0x1400051d8  jmp     loc_140005116
0x1400051dd  mov     edx, [rbx+6]
0x1400051e0  mov     ecx, 2
0x1400051e5  call    ?IsCommandOnAllowList@Tpm20Scheduler@@CA_NW4_USER_TYPE@@I@Z; Tpm20Scheduler::IsCommandOnAllowList(_USER_TYPE,uint)
0x1400051ea  test    al, al
0x1400051ec  jz      loc_140005132
0x1400051f2  mov     al, 1
0x1400051f4  jmp     loc_14000516A
0x1400051f9  cmp     eax, 2
0x1400051fc  jnz     loc_140005132
0x140005202  call    ?IsWinPE@TpmRegistry@@SA_NXZ; TpmRegistry::IsWinPE(void)
0x140005207  test    al, al
0x140005209  jz      loc_140005132
0x14000520f  mov     al, 1
0x140005211  jmp     loc_14000516A
```
