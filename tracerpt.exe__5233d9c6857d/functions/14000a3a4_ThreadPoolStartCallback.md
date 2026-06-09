# ThreadPoolStartCallback

- ea: `0x14000a3a4`
- end: `0x14000a45f`
- name: `ThreadPoolStartCallback`
- size: `187`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140003a30`

## callees

- `0x140004c2c`
- `0x14000a3a4`
- `0x14001d51c`

## string_xrefs

- `0x14000a41b`: `TaskId`

## pseudocode

```c
int __fastcall ThreadPoolStartCallback(PEVENT_RECORD Event, __int64 a2)
{
  struct _SERVICE_RECORD *v2; // rax
  bool v3; // zf
  _UNKNOWN *retaddr; // [rsp+28h] [rbp+0h] BYREF
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF
  int v10; // [rsp+40h] [rbp+18h] BYREF

  v2 = (struct _SERVICE_RECORD *)&retaddr;
  v3 = *(_DWORD *)(a2 + 552) == 0;
  v9 = 0;
  *(_BYTE *)(a2 + 544) = 1;
  if ( v3 )
  {
    v8 = 4;
    LODWORD(v2) = GetMofData(Event, L"SubProcessTag", &v9, &v8);
    if ( !(_DWORD)v2 )
    {
      v2 = FindOrAddService(v9, Event->EventHeader.ProcessId);
      if ( v2 )
      {
        v10 = 0;
        v8 = 4;
        LODWORD(v2) = GetMofData(Event, L"TaskId", &v10, &v8);
        if ( !(_DWORD)v2 )
        {
          *(_DWORD *)(a2 + 552) = v10;
          *(_DWORD *)(a2 + 548) = v9;
          *(_DWORD *)(a2 + 556) = Event->EventHeader.KernelTime;
          LODWORD(v2) = Event->EventHeader.UserTime;
          *(_DWORD *)(a2 + 560) = (_DWORD)v2;
        }
      }
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x14000a3a4  mov     rax, rsp
0x14000a3a7  mov     [rax+20h], rbx
0x14000a3ab  push    rdi
0x14000a3ac  sub     rsp, 20h
0x14000a3b0  cmp     dword ptr [rdx+228h], 0
0x14000a3b7  mov     rbx, rdx
0x14000a3ba  mov     rdi, rcx
0x14000a3bd  mov     dword ptr [rax+10h], 0
0x14000a3c4  mov     byte ptr [rdx+220h], 1
0x14000a3cb  jnz     loc_14000A454
0x14000a3d1  lea     r9, [rax+8]; unsigned int *
0x14000a3d5  mov     dword ptr [rax+8], 4
0x14000a3dc  lea     r8, [rax+10h]; void *
0x14000a3e0  lea     rdx, aSubprocesstag; "SubProcessTag"
0x14000a3e7  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000a3ec  test    eax, eax
0x14000a3ee  jnz     short loc_14000A454
0x14000a3f0  mov     edx, [rdi+0Ch]; unsigned int
0x14000a3f3  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x14000a3f7  call    ?FindOrAddService@@YAPEAU_SERVICE_RECORD@@KK@Z; FindOrAddService(ulong,ulong)
0x14000a3fc  test    rax, rax
0x14000a3ff  jz      short loc_14000A454
0x14000a401  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x14000a406  mov     [rsp+28h+arg_10], 0
0x14000a40e  lea     r8, [rsp+28h+arg_10]; void *
0x14000a413  mov     [rsp+28h+arg_0], 4
0x14000a41b  lea     rdx, aTaskid; "TaskId"
0x14000a422  mov     rcx, rdi; Event
0x14000a425  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000a42a  test    eax, eax
0x14000a42c  jnz     short loc_14000A454
0x14000a42e  mov     eax, [rsp+28h+arg_10]
0x14000a432  mov     [rbx+228h], eax
0x14000a438  mov     eax, [rsp+28h+arg_8]
0x14000a43c  mov     [rbx+224h], eax
0x14000a442  mov     eax, [rdi+38h]
0x14000a445  mov     [rbx+22Ch], eax
0x14000a44b  mov     eax, [rdi+3Ch]
0x14000a44e  mov     [rbx+230h], eax
0x14000a454  mov     rbx, [rsp+28h+arg_18]
0x14000a459  add     rsp, 20h
0x14000a45d  pop     rdi
0x14000a45e  retn
```
