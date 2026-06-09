# CVssDebugInfo::~CVssDebugInfo(void)

- ea: `0x180033c2c`
- end: `0x180033c71`
- name: `??1CVssDebugInfo@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CVssDebugInfo *__hidden this)`
- caller_count: `58`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800048f8`
- `0x180004944`
- `0x180006910`
- `0x180011178`
- `0x180017410`
- `0x18001b130`
- `0x18001f47c`
- `0x180020c6c`
- `0x180021bc4`
- `0x180025c40`
- `0x18002a774`
- `0x180033a8c`
- `0x180034278`
- `0x180034324`
- `0x180034484`
- `0x180034754`
- `0x1800348b4`
- `0x180034a4c`
- `0x180034cfc`
- `0x1800358f4`
- `0x180035f44`
- `0x18003609c`
- `0x180036218`
- `0x180036614`
- `0x1800367b8`
- `0x1800368c4`
- `0x1800369ac`
- `0x180036af8`
- `0x180036c10`
- `0x180036e8c`
- `0x180036f10`
- `0x180037080`
- `0x18003725c`
- `0x1800372e8`
- `0x18003750c`
- `0x1800377c4`
- `0x18003ced0`
- `0x18003e960`
- `0x1800402e4`
- `0x180040cb0`
- `0x180041c4f`
- `0x1800459e1`
- `0x18004818c`
- `0x180048e4c`
- `0x180048e70`
- `0x180048ea6`
- `0x180048f4f`
- `0x180048f73`
- `0x180049016`
- `0x1800491bd`

## callees

- `0x180033c2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c4e`

## pseudocode

```c
void __fastcall CVssDebugInfo::~CVssDebugInfo(CVssDebugInfo *this)
{
  __int64 i; // rbx
  void *v3; // rcx

  if ( *((_BYTE *)this + 163) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v3 = (void *)*((_QWORD *)this + i + 5);
      if ( v3 )
      {
        CoTaskMemFree(v3);
        *((_QWORD *)this + i + 5) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180033c2c  mov     [rsp+arg_0], rbx
0x180033c31  push    rdi
0x180033c32  sub     rsp, 20h
0x180033c36  cmp     byte ptr [rcx+0A3h], 0
0x180033c3d  mov     rdi, rcx
0x180033c40  jz      short loc_180033C66
0x180033c42  xor     ebx, ebx
0x180033c44  mov     rcx, [rdi+rbx*8+28h]; pv
0x180033c49  test    rcx, rcx
0x180033c4c  jz      short loc_180033C5D
0x180033c4e  call    cs:__imp_CoTaskMemFree
0x180033c54  mov     qword ptr [rdi+rbx*8+28h], 0
0x180033c5d  inc     rbx
0x180033c60  cmp     rbx, 0Fh
0x180033c64  jnz     short loc_180033C44
0x180033c66  mov     rbx, [rsp+28h+arg_0]
0x180033c6b  add     rsp, 20h
0x180033c6f  pop     rdi
0x180033c70  retn
```
