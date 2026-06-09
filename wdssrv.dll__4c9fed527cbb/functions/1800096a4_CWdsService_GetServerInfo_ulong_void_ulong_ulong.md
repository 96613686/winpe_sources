# CWdsService::GetServerInfo(ulong,void *,ulong,ulong *)

- ea: `0x1800096a4`
- end: `0x1800097c0`
- name: `?GetServerInfo@CWdsService@@QEAAKKPEAXKPEAK@Z`
- size: `284`
- prototype: `unsigned int(CWdsService *__hidden this, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011810`

## callees

- `0x1800096a4`
- `0x18000f0dc`
- `0x18001c112`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000971d`
- `KERNEL32!LeaveCriticalSection` at `0x18000971d`
- `KERNEL32!EnterCriticalSection` at `0x1800096f0`
- `KERNEL32!EnterCriticalSection` at `0x1800096f0`
- `WdsServerCommonLib!?IsEnabled@CTrace@@QEAAHXZ` at `0x180009790`
- `WdsServerCommonLib!?IsEnabled@CTrace@@QEAAHXZ` at `0x180009790`

## pseudocode

```c
__int64 __fastcall CWdsService::GetServerInfo(CWdsService *this, int a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v5; // ebx
  __int64 v9; // rdx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8

  v5 = 0;
  v9 = (unsigned int)(a2 - 1);
  if ( (_DWORD)v9 )
  {
    if ( (_DWORD)v9 == 1 )
    {
      v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 67320);
      EnterCriticalSection((LPCRITICAL_SECTION)this + 1683);
      if ( dword_180028B90 || (v5 = 5023, !(unsigned int)ElValidateWin32_0(0x139Fu, v11, v12, 0x25Au)) )
      {
        if ( a4 >= *((_DWORD *)this + 16840) || (v5 = 122, !(unsigned int)ElValidateWin32_0(0x7Au, v11, v12, 0x260u)) )
        {
          memcpy_0(a3, *((const void **)this + 8421), *((unsigned int *)this + 16840));
          *a5 = *((_DWORD *)this + 16840);
        }
      }
      LeaveCriticalSection(v10);
    }
    else
    {
      v5 = 87;
      ElValidateWin32_0(0x57u, v9, (__int64)a3, 0x26Au);
    }
  }
  else if ( a4 == 4 || (v5 = 122, !(unsigned int)ElValidateWin32_0(0x7Au, v9, (__int64)a3, 0x24Cu)) )
  {
    *a3 = CTrace::IsEnabled((CTrace *)qword_180039310);
    *a5 = 4;
  }
  return v5;
}

```

## disassembly

```asm
0x1800096a4  mov     [rsp+arg_0], rbx
0x1800096a9  mov     [rsp+arg_10], rbp
0x1800096ae  push    rsi
0x1800096af  push    rdi
0x1800096b0  push    r14
0x1800096b2  sub     rsp, 20h
0x1800096b6  xor     ebx, ebx
0x1800096b8  mov     ebp, r9d
0x1800096bb  mov     r14, r8
0x1800096be  mov     rsi, rcx
0x1800096c1  sub     edx, 1
0x1800096c4  jz      loc_18000976E
0x1800096ca  cmp     edx, 1
0x1800096cd  jz      short loc_1800096E6
0x1800096cf  mov     ebx, 57h ; 'W'
0x1800096d4  mov     r9d, 26Ah
0x1800096da  mov     ecx, ebx
0x1800096dc  call    ElValidateWin32_0
0x1800096e1  jmp     loc_1800097AA
0x1800096e6  lea     rdi, [rcx+106F8h]
0x1800096ed  mov     rcx, rdi; lpCriticalSection
0x1800096f0  call    cs:__imp_EnterCriticalSection
0x1800096f7  nop     dword ptr [rax+rax+00h]
0x1800096fc  cmp     cs:dword_180028B90, ebx
0x180009702  jnz     short loc_18000972B
0x180009704  mov     ebx, 139Fh
0x180009709  mov     r9d, 25Ah
0x18000970f  mov     ecx, ebx
0x180009711  call    ElValidateWin32_0
0x180009716  test    eax, eax
0x180009718  jz      short loc_18000972B
0x18000971a  mov     rcx, rdi; lpCriticalSection
0x18000971d  call    cs:__imp_LeaveCriticalSection
0x180009724  nop     dword ptr [rax+rax+00h]
0x180009729  jmp     short loc_1800097AA
0x18000972b  cmp     ebp, [rsi+10720h]
0x180009731  jnb     short loc_180009749
0x180009733  mov     ecx, 7Ah ; 'z'
0x180009738  mov     r9d, 260h
0x18000973e  mov     ebx, ecx
0x180009740  call    ElValidateWin32_0
0x180009745  test    eax, eax
0x180009747  jnz     short loc_18000971A
0x180009749  mov     r8d, [rsi+10720h]; Size
0x180009750  mov     rcx, r14; void *
0x180009753  mov     rdx, [rsi+10728h]; Src
0x18000975a  call    memcpy_0
0x18000975f  mov     rax, [rsp+38h+arg_20]
0x180009764  mov     ecx, [rsi+10720h]
0x18000976a  mov     [rax], ecx
0x18000976c  jmp     short loc_18000971A
0x18000976e  cmp     ebp, 4
0x180009771  jz      short loc_180009789
0x180009773  mov     ecx, 7Ah ; 'z'
0x180009778  mov     r9d, 24Ch
0x18000977e  mov     ebx, ecx
0x180009780  call    ElValidateWin32_0
0x180009785  test    eax, eax
0x180009787  jnz     short loc_1800097AA
0x180009789  lea     rcx, qword_180039310
0x180009790  call    cs:__imp_?IsEnabled@CTrace@@QEAAHXZ; CTrace::IsEnabled(void)
0x180009797  nop     dword ptr [rax+rax+00h]
0x18000979c  mov     rcx, [rsp+38h+arg_20]
0x1800097a1  mov     [r14], eax
0x1800097a4  mov     dword ptr [rcx], 4
0x1800097aa  mov     rbp, [rsp+38h+arg_10]
0x1800097af  mov     eax, ebx
0x1800097b1  mov     rbx, [rsp+38h+arg_0]
0x1800097b6  add     rsp, 20h
0x1800097ba  pop     r14
0x1800097bc  pop     rdi
0x1800097bd  pop     rsi
0x1800097be  retn
```
