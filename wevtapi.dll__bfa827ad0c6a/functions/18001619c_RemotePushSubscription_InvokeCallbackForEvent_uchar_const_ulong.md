# RemotePushSubscription::InvokeCallbackForEvent(uchar * const,ulong)

- ea: `0x18001619c`
- end: `0x180016227`
- name: `?InvokeCallbackForEvent@RemotePushSubscription@@AEAAXQEAEK@Z`
- size: `139`
- prototype: `void __fastcall(RemotePushSubscription *this, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016034`

## callees

- `0x18001619c`
- `0x180016314`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800161d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800161d7`

## pseudocode

```c
void __fastcall RemotePushSubscription::InvokeCallbackForEvent(
        RemotePushSubscription *this,
        unsigned int *a2,
        unsigned int a3)
{
  Event::SetData(*((_QWORD *)this + 24), (__int64)this + 216, a2, a3);
  *(_BYTE *)(*((_QWORD *)this + 24) + 29LL) = 1;
  if ( *((_QWORD *)this + 4) )
  {
    *((_DWORD *)this + 85) = GetCurrentThreadId();
    (*((void (__fastcall **)(__int64, _QWORD, _QWORD))this + 4))(
      1,
      *((_QWORD *)this + 5),
      *(_QWORD *)(*((_QWORD *)this + 24) + 16LL));
    *((_DWORD *)this + 85) = 0;
  }
  *(_BYTE *)(*((_QWORD *)this + 24) + 29LL) = 0;
}

```

## disassembly

```asm
0x18001619c  push    rbx
0x18001619e  sub     rsp, 40h
0x1800161a2  mov     rax, rdx
0x1800161a5  mov     rbx, rcx
0x1800161a8  lea     rdx, [rcx+0D8h]
0x1800161af  mov     r9d, r8d
0x1800161b2  mov     r8, rax
0x1800161b5  mov     rcx, [rcx+0C0h]
0x1800161bc  call    ?SetData@Event@@QEAAXAEAV?$AutoRef@VBookmarkChannels@@@wmi@@PEAEK_NPEAVBinXmlTemplateTable@@@Z; Event::SetData(wmi::AutoRef<BookmarkChannels> &,uchar *,ulong,bool,BinXmlTemplateTable *)
0x1800161c1  mov     rdx, [rbx+0C0h]
0x1800161c8  mov     eax, 1
0x1800161cd  xchg    al, [rdx+1Dh]
0x1800161d0  cmp     qword ptr [rbx+20h], 0
0x1800161d5  jz      short loc_180016215
0x1800161d7  call    cs:__imp_GetCurrentThreadId
0x1800161dd  mov     [rbx+154h], eax
0x1800161e3  mov     [rsp+48h+var_18], rbx
0x1800161e8  mov     [rsp+48h+var_10], 1
0x1800161ed  mov     r8, [rbx+0C0h]
0x1800161f4  mov     r8, [r8+10h]
0x1800161f8  mov     rdx, [rbx+28h]
0x1800161fc  mov     ecx, 1
0x180016201  mov     rax, [rbx+20h]
0x180016205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001620a  nop
0x18001620b  mov     dword ptr [rbx+154h], 0
0x180016215  mov     rcx, [rbx+0C0h]
0x18001621c  xor     eax, eax
0x18001621e  xchg    al, [rcx+1Dh]
0x180016221  add     rsp, 40h
0x180016225  pop     rbx
0x180016226  retn
```
