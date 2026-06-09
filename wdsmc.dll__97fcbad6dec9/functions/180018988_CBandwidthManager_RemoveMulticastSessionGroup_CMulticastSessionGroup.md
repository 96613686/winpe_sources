# CBandwidthManager::RemoveMulticastSessionGroup(CMulticastSessionGroup *)

- ea: `0x180018988`
- end: `0x180018b7d`
- name: `?RemoveMulticastSessionGroup@CBandwidthManager@@QEAAKPEAVCMulticastSessionGroup@@@Z`
- size: `501`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CMulticastSessionGroup *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x1800193f8`

## callees

- `0x180018488`
- `0x18001853c`
- `0x180018988`
- `0x18001a9a8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800189c6`
- `KERNEL32!LeaveCriticalSection` at `0x180018a8d`
- `KERNEL32!LeaveCriticalSection` at `0x180018abb`
- `KERNEL32!LeaveCriticalSection` at `0x180018b5b`
- `KERNEL32!LeaveCriticalSection` at `0x1800189c6`
- `KERNEL32!LeaveCriticalSection` at `0x180018a8d`
- `KERNEL32!LeaveCriticalSection` at `0x180018abb`
- `KERNEL32!LeaveCriticalSection` at `0x180018b5b`
- `KERNEL32!EnterCriticalSection` at `0x1800189a6`
- `KERNEL32!EnterCriticalSection` at `0x1800189b6`
- `KERNEL32!EnterCriticalSection` at `0x1800189ed`
- `KERNEL32!EnterCriticalSection` at `0x180018aae`
- `KERNEL32!EnterCriticalSection` at `0x1800189a6`
- `KERNEL32!EnterCriticalSection` at `0x1800189b6`
- `KERNEL32!EnterCriticalSection` at `0x1800189ed`
- `KERNEL32!EnterCriticalSection` at `0x180018aae`

## pseudocode

```c
__int64 __fastcall CBandwidthManager::RemoveMulticastSessionGroup(
        char *lpCriticalSection,
        struct CMulticastSessionGroup *a2)
{
  PRTL_CRITICAL_SECTION_DEBUG v4; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v5; // rsi
  struct CMulticastSessionGroup **v6; // rcx
  int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  struct CMulticastSessionGroup *v12; // rdx
  struct CMulticastSessionGroup *v13; // rdx
  unsigned int v14; // r14d
  int v15; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v16; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v17; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v18; // rax
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 216));
  v4 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 25);
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 216));
  if ( v4 && (v5 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 25)) != 0 )
  {
    while ( 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
      v6 = *(struct CMulticastSessionGroup ***)&v5->EntryCount;
      v7 = 1;
      while ( v6 )
      {
        if ( *v6 == a2 )
        {
          if ( *(_DWORD *)&v5[1].Type == 1 )
          {
            *(_QWORD *)&v5->Flags = 0;
            *(_QWORD *)&v5->EntryCount = 0;
          }
          else
          {
            v8 = *(_QWORD *)&v5->EntryCount;
            if ( v6 == (struct CMulticastSessionGroup **)v8 )
            {
              v9 = *(_QWORD *)(v8 + 16);
              *(_QWORD *)&v5->EntryCount = v9;
              *(_QWORD *)(v9 + 8) = 0;
            }
            else
            {
              v10 = *(_QWORD *)&v5->Flags;
              if ( v6 == (struct CMulticastSessionGroup **)v10 )
              {
                v11 = *(_QWORD *)(v10 + 8);
                *(_QWORD *)&v5->Flags = v11;
                *(_QWORD *)(v11 + 16) = 0;
              }
              else
              {
                v12 = v6[1];
                if ( v12 )
                  *((_QWORD *)v12 + 2) = v6[2];
                v13 = v6[2];
                if ( v13 )
                  *((_QWORD *)v13 + 1) = v6[1];
              }
            }
          }
          operator delete(v6);
          --*(_DWORD *)&v5[1].Type;
          v7 = 0;
          CBandwidthManager::UpdateMulticastSessionGroups(
            (LPCRITICAL_SECTION)lpCriticalSection,
            (struct CBandwidthManager::Interface *)v5);
          break;
        }
        v6 = (struct CMulticastSessionGroup **)v6[2];
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
      v14 = 2 * v7;
      if ( !v14 )
        break;
      v5 = *(PRTL_CRITICAL_SECTION_DEBUG *)&v5[2].Type;
      if ( !v5 )
        goto LABEL_32;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)&v5[1].CriticalSection);
    v15 = *(_DWORD *)&v5[1].Type;
    LeaveCriticalSection((LPCRITICAL_SECTION)&v5[1].CriticalSection);
    if ( !v15 )
    {
      v16 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 25);
      v17 = (struct _RTL_CRITICAL_SECTION_DEBUG *)*((_QWORD *)lpCriticalSection + 26);
      if ( v16 == v17 )
      {
        *((_QWORD *)lpCriticalSection + 26) = 0;
        *((_QWORD *)lpCriticalSection + 25) = 0;
      }
      else if ( v5 == v16 )
      {
        v18 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&v16[2].Type;
        *((_QWORD *)lpCriticalSection + 25) = v18;
        v18[2].CriticalSection = 0;
      }
      else if ( v5 == v17 )
      {
        CriticalSection = v17[2].CriticalSection;
        *((_QWORD *)lpCriticalSection + 26) = CriticalSection;
        CriticalSection[2].OwningThread = 0;
      }
      else
      {
        v5[2].CriticalSection[2].OwningThread = *(HANDLE *)&v5[2].Type;
        *(_QWORD *)(*(_QWORD *)&v5[2].Type + 104LL) = v5[2].CriticalSection;
      }
      --*((_DWORD *)lpCriticalSection + 64);
      CBandwidthManager::Interface::`scalar deleting destructor'((CBandwidthManager::Interface *)v5);
    }
  }
  else
  {
    v14 = 2;
  }
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  return v14;
}

```

## disassembly

```asm
0x180018988  mov     [rsp+arg_0], rbx
0x18001898d  mov     [rsp+arg_8], rbp
0x180018992  mov     [rsp+arg_10], rsi
0x180018997  push    rdi
0x180018998  push    r14
0x18001899a  push    r15
0x18001899c  sub     rsp, 20h
0x1800189a0  mov     r15, rdx
0x1800189a3  mov     rbp, rcx
0x1800189a6  call    cs:__imp_EnterCriticalSection
0x1800189ac  lea     rbx, [rbp+0D8h]
0x1800189b3  mov     rcx, rbx; lpCriticalSection
0x1800189b6  call    cs:__imp_EnterCriticalSection
0x1800189bc  mov     rdi, [rbp+0C8h]
0x1800189c3  mov     rcx, rbx; lpCriticalSection
0x1800189c6  call    cs:__imp_LeaveCriticalSection
0x1800189cc  test    rdi, rdi
0x1800189cf  jz      loc_180018B52
0x1800189d5  mov     rsi, [rbp+0C8h]
0x1800189dc  test    rsi, rsi
0x1800189df  jz      loc_180018B52
0x1800189e5  mov     ebx, 1
0x1800189ea  mov     rcx, rbp; lpCriticalSection
0x1800189ed  call    cs:__imp_EnterCriticalSection
0x1800189f3  mov     rcx, [rsi+20h]
0x1800189f7  mov     r14d, ebx
0x1800189fa  jmp     short loc_180018A05
0x1800189fc  cmp     [rcx], r15
0x1800189ff  jz      short loc_180018A0C
0x180018a01  mov     rcx, [rcx+10h]; void *
0x180018a05  test    rcx, rcx
0x180018a08  jnz     short loc_1800189FC
0x180018a0a  jmp     short loc_180018A8A
0x180018a0c  test    rcx, rcx
0x180018a0f  jz      short loc_180018A7C
0x180018a11  cmp     [rsi+30h], ebx
0x180018a14  jnz     short loc_180018A22
0x180018a16  and     qword ptr [rsi+28h], 0
0x180018a1b  and     qword ptr [rsi+20h], 0
0x180018a20  jmp     short loc_180018A74
0x180018a22  mov     rax, [rsi+20h]
0x180018a26  cmp     rcx, rax
0x180018a29  jnz     short loc_180018A3A
0x180018a2b  mov     rax, [rax+10h]
0x180018a2f  mov     [rsi+20h], rax
0x180018a33  and     qword ptr [rax+8], 0
0x180018a38  jmp     short loc_180018A74
0x180018a3a  mov     rax, [rsi+28h]
0x180018a3e  cmp     rcx, rax
0x180018a41  jnz     short loc_180018A52
0x180018a43  mov     rax, [rax+8]
0x180018a47  mov     [rsi+28h], rax
0x180018a4b  and     qword ptr [rax+10h], 0
0x180018a50  jmp     short loc_180018A74
0x180018a52  mov     rdx, [rcx+8]
0x180018a56  test    rdx, rdx
0x180018a59  jz      short loc_180018A63
0x180018a5b  mov     rax, [rcx+10h]
0x180018a5f  mov     [rdx+10h], rax
0x180018a63  mov     rdx, [rcx+10h]
0x180018a67  test    rdx, rdx
0x180018a6a  jz      short loc_180018A74
0x180018a6c  mov     rax, [rcx+8]
0x180018a70  mov     [rdx+8], rax
0x180018a74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018a79  dec     dword ptr [rsi+30h]
0x180018a7c  xor     r14d, r14d
0x180018a7f  mov     rdx, rsi; struct CBandwidthManager::Interface *
0x180018a82  mov     rcx, rbp; lpCriticalSection
0x180018a85  call    ?UpdateMulticastSessionGroups@CBandwidthManager@@AEAAXPEAUInterface@1@@Z; CBandwidthManager::UpdateMulticastSessionGroups(CBandwidthManager::Interface *)
0x180018a8a  mov     rcx, rbp; lpCriticalSection
0x180018a8d  call    cs:__imp_LeaveCriticalSection
0x180018a93  add     r14d, r14d
0x180018a96  jz      short loc_180018AAA
0x180018a98  mov     rsi, [rsi+60h]
0x180018a9c  test    rsi, rsi
0x180018a9f  jnz     loc_1800189EA
0x180018aa5  jmp     loc_180018B58
0x180018aaa  lea     rcx, [rsi+38h]; lpCriticalSection
0x180018aae  call    cs:__imp_EnterCriticalSection
0x180018ab4  mov     ebx, [rsi+30h]
0x180018ab7  lea     rcx, [rsi+38h]; lpCriticalSection
0x180018abb  call    cs:__imp_LeaveCriticalSection
0x180018ac1  test    ebx, ebx
0x180018ac3  jnz     loc_180018B58
0x180018ac9  test    rsi, rsi
0x180018acc  jz      loc_180018B58
0x180018ad2  mov     rax, [rbp+0C8h]
0x180018ad9  mov     rcx, [rbp+0D0h]
0x180018ae0  cmp     rax, rcx
0x180018ae3  jnz     short loc_180018AF7
0x180018ae5  and     qword ptr [rbp+0D0h], 0
0x180018aed  and     qword ptr [rbp+0C8h], 0
0x180018af5  jmp     short loc_180018B3D
0x180018af7  cmp     rsi, rax
0x180018afa  jnz     short loc_180018B0E
0x180018afc  mov     rax, [rax+60h]
0x180018b00  mov     [rbp+0C8h], rax
0x180018b07  and     qword ptr [rax+68h], 0
0x180018b0c  jmp     short loc_180018B3D
0x180018b0e  cmp     rsi, rcx
0x180018b11  jnz     short loc_180018B25
0x180018b13  mov     rax, [rcx+68h]
0x180018b17  mov     [rbp+0D0h], rax
0x180018b1e  and     qword ptr [rax+60h], 0
0x180018b23  jmp     short loc_180018B3D
0x180018b25  mov     rdx, [rsi+68h]
0x180018b29  mov     rax, [rsi+60h]
0x180018b2d  mov     [rdx+60h], rax
0x180018b31  mov     rdx, [rsi+60h]; unsigned int
0x180018b35  mov     rax, [rsi+68h]
0x180018b39  mov     [rdx+68h], rax
0x180018b3d  dec     dword ptr [rbp+100h]
0x180018b43  test    rsi, rsi
0x180018b46  jz      short loc_180018B58
0x180018b48  mov     rcx, rsi; this
0x180018b4b  call    ??_GInterface@CBandwidthManager@@QEAAPEAXI@Z; CBandwidthManager::Interface::`scalar deleting destructor'(uint)
0x180018b50  jmp     short loc_180018B58
0x180018b52  mov     r14d, 2
0x180018b58  mov     rcx, rbp; lpCriticalSection
0x180018b5b  call    cs:__imp_LeaveCriticalSection
0x180018b61  mov     rbx, [rsp+38h+arg_0]
0x180018b66  mov     eax, r14d
0x180018b69  mov     rbp, [rsp+38h+arg_8]
0x180018b6e  mov     rsi, [rsp+38h+arg_10]
0x180018b73  add     rsp, 20h
0x180018b77  pop     r15
0x180018b79  pop     r14
0x180018b7b  pop     rdi
0x180018b7c  retn
```
